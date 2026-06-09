# WinHvpAddRemovePhysicalMemory

- ea: `0x140022bc0`
- end: `0x140022d48`
- name: `WinHvpAddRemovePhysicalMemory`
- size: `392`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140008eb0`
- `0x140009000`

## callees

- `0x140002358`
- `0x140004564`
- `0x1400058b8`
- `0x140022af0`
- `0x140022bc0`

## pseudocode

```c
__int64 __fastcall WinHvpAddRemovePhysicalMemory(char a1, __int64 a2, __int64 a3, unsigned __int64 a4, _QWORD *a5)
{
  _QWORD *v5; // r15
  int v6; // r13d
  int v7; // ebx
  char v11; // dl
  char v12; // dl
  char v13; // si
  unsigned __int64 v14; // rax
  __int128 *v15; // rdx
  __int64 v16; // rcx
  unsigned int v17; // eax
  __int64 v18; // rsi
  __int128 v20; // [rsp+30h] [rbp-28h] BYREF
  __int128 v21; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v22; // [rsp+A0h] [rbp+48h] BYREF

  v5 = a5;
  v6 = 0;
  v7 = 0;
  v22 = 0;
  *a5 = 0;
  v20 = 0;
  v21 = 0;
  if ( a1 )
  {
    WinHvpInitializeFastHypercall(&v20);
    LOBYTE(v20) = v11;
  }
  else
  {
    WinHvpInitializeFastHypercall(&v21);
    LOBYTE(v21) = v12;
  }
  while ( a4 )
  {
    v13 = 0;
    if ( a4 <= 0xFFF )
    {
      LODWORD(v14) = a4;
    }
    else if ( (a3 & 0x1FF) != 0 )
    {
      LODWORD(v14) = 4095;
      if ( a4 > 0x1FFE )
        LODWORD(v14) = 4095 - (a3 & 0x1FF);
    }
    else
    {
      v13 = 1;
      v14 = a4 >> 9;
      if ( a4 >> 9 >= 0xFFF )
        LODWORD(v14) = 4095;
    }
    if ( a1 )
    {
      *((_QWORD *)&v20 + 1) = a3;
      v15 = &v20;
      BYTE1(v20) = v13;
      v16 = 188;
    }
    else
    {
      *((_QWORD *)&v21 + 1) = a3;
      v15 = &v21;
      BYTE1(v21) = v13;
      v16 = 247;
    }
    v7 = WinHvpFastRepHypercall(v16, v15, (unsigned int)v14, &v22);
    v17 = v22;
    if ( v13 )
    {
      v17 = v22 << 9;
      v22 <<= 9;
    }
    v18 = v17;
    *v5 += v17;
    if ( v7 == -1070268299 || v7 == -1070268405 || (unsigned int)(v7 + 1070268287) <= 1 )
    {
      v7 = WinHvpLowMemoryHandler(-1, -2147418113, v7, a1 != 0 ? 188 : 247, v6, 0);
      if ( v7 < 0 )
      {
        v7 = -1073741670;
        break;
      }
    }
    else if ( v7 < 0 )
    {
      break;
    }
    a4 -= v18;
    a3 += v18;
    ++v6;
  }
  if ( !a1 && *v5 )
    WinHvWithdrawAllMemoryWithCount(-1, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140022bc0  push    rbp
0x140022bc2  push    rbx
0x140022bc3  push    rsi
0x140022bc4  push    rdi
0x140022bc5  push    r12
0x140022bc7  push    r13
0x140022bc9  push    r14
0x140022bcb  push    r15
0x140022bcd  mov     rbp, rsp
0x140022bd0  sub     rsp, 58h
0x140022bd4  mov     r15, [rbp+arg_20]
0x140022bd8  xor     r13d, r13d
0x140022bdb  xor     ebx, ebx
0x140022bdd  mov     [rbp+arg_0], 0
0x140022be4  xorps   xmm0, xmm0
0x140022be7  xorps   xmm1, xmm1
0x140022bea  mov     rdi, r9
0x140022bed  mov     r14, r8
0x140022bf0  mov     qword ptr [r15], 0
0x140022bf7  mov     r12b, cl
0x140022bfa  movups  [rbp+var_28], xmm0
0x140022bfe  movups  [rbp+var_18], xmm1
0x140022c02  test    cl, cl
0x140022c04  jz      short loc_140022C14
0x140022c06  lea     rcx, [rbp+var_28]
0x140022c0a  call    WinHvpInitializeFastHypercall
0x140022c0f  mov     byte ptr [rbp+var_28], dl
0x140022c12  jmp     short loc_140022C20
0x140022c14  lea     rcx, [rbp+var_18]
0x140022c18  call    WinHvpInitializeFastHypercall
0x140022c1d  mov     byte ptr [rbp+var_18], dl
0x140022c20  mov     edx, 0FFFh
0x140022c25  test    rdi, rdi
0x140022c28  jz      loc_140022D1E
0x140022c2e  xor     sil, sil
0x140022c31  cmp     rdi, rdx
0x140022c34  jbe     short loc_140022C6A
0x140022c36  test    r14, 1FFh
0x140022c3d  jnz     short loc_140022C52
0x140022c3f  mov     rax, rdi
0x140022c42  mov     sil, 1
0x140022c45  shr     rax, 9
0x140022c49  cmp     rax, rdx
0x140022c4c  jb      short loc_140022C6C
0x140022c4e  mov     eax, edx
0x140022c50  jmp     short loc_140022C6C
0x140022c52  mov     eax, edx
0x140022c54  cmp     rdi, 1FFEh
0x140022c5b  jbe     short loc_140022C6C
0x140022c5d  mov     ecx, r14d
0x140022c60  and     ecx, 1FFh
0x140022c66  sub     eax, ecx
0x140022c68  jmp     short loc_140022C6C
0x140022c6a  mov     eax, edi
0x140022c6c  lea     r9, [rbp+arg_0]
0x140022c70  mov     r8d, eax
0x140022c73  test    r12b, r12b
0x140022c76  jz      short loc_140022C8B
0x140022c78  mov     qword ptr [rbp+var_28+8], r14
0x140022c7c  lea     rdx, [rbp+var_28]
0x140022c80  mov     byte ptr [rbp+var_28+1], sil
0x140022c84  mov     ecx, 0BCh
0x140022c89  jmp     short loc_140022C9C
0x140022c8b  mov     qword ptr [rbp+var_18+8], r14
0x140022c8f  lea     rdx, [rbp+var_18]
0x140022c93  mov     byte ptr [rbp+var_18+1], sil
0x140022c97  mov     ecx, 0F7h
0x140022c9c  call    WinHvpFastRepHypercall
0x140022ca1  mov     ebx, eax
0x140022ca3  mov     eax, [rbp+arg_0]
0x140022ca6  test    sil, sil
0x140022ca9  jz      short loc_140022CB1
0x140022cab  shl     eax, 9
0x140022cae  mov     [rbp+arg_0], eax
0x140022cb1  mov     esi, eax
0x140022cb3  add     [r15], rsi
0x140022cb6  cmp     ebx, 0C0350075h
0x140022cbc  jz      short loc_140022CD7
0x140022cbe  cmp     ebx, 0C035000Bh
0x140022cc4  jz      short loc_140022CD7
0x140022cc6  lea     eax, [rbx+3FCAFF7Fh]
0x140022ccc  cmp     eax, 1
0x140022ccf  jbe     short loc_140022CD7
0x140022cd1  test    ebx, ebx
0x140022cd3  js      short loc_140022D1E
0x140022cd5  jmp     short loc_140022D0B
0x140022cd7  mov     al, r12b
0x140022cda  mov     [rsp+58h+var_30], 0
0x140022cdf  neg     al
0x140022ce1  mov     [rsp+58h+var_38], r13d
0x140022ce6  mov     r8d, ebx
0x140022ce9  mov     edx, 8000FFFFh
0x140022cee  sbb     r9d, r9d
0x140022cf1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140022cf5  and     r9d, 0FFFFFFC5h
0x140022cf9  add     r9d, 0F7h
0x140022d00  call    WinHvpLowMemoryHandler
0x140022d05  mov     ebx, eax
0x140022d07  test    eax, eax
0x140022d09  js      short loc_140022D19
0x140022d0b  sub     rdi, rsi
0x140022d0e  add     r14, rsi
0x140022d11  inc     r13d
0x140022d14  jmp     loc_140022C20
0x140022d19  mov     ebx, 0C000009Ah
0x140022d1e  test    r12b, r12b
0x140022d21  jnz     short loc_140022D34
0x140022d23  cmp     qword ptr [r15], 0
0x140022d27  jbe     short loc_140022D34
0x140022d29  xor     edx, edx
0x140022d2b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140022d2f  call    WinHvWithdrawAllMemoryWithCount
0x140022d34  mov     eax, ebx
0x140022d36  add     rsp, 58h
0x140022d3a  pop     r15
0x140022d3c  pop     r14
0x140022d3e  pop     r13
0x140022d40  pop     r12
0x140022d42  pop     rdi
0x140022d43  pop     rsi
0x140022d44  pop     rbx
0x140022d45  pop     rbp
0x140022d46  retn
```

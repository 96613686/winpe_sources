# SkmiQueryImageExtensionInformation

- ea: `0x140066b20`
- end: `0x140066da4`
- name: `SkmiQueryImageExtensionInformation`
- size: `644`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x140067ecc`

## callees

- `0x14000e810`
- `0x14000ff70`
- `0x14001e518`
- `0x14001e5e0`
- `0x140066b20`
- `0x1400802ac`
- `0x1400d4e8c`
- `0x1400f3620`
- `0x1400f38f0`
- `0x1400fc554`

## pseudocode

```c
__int64 __fastcall SkmiQueryImageExtensionInformation(
        void *a1,
        unsigned __int64 a2,
        char a3,
        unsigned __int64 a4,
        _QWORD *a5)
{
  char v6; // r14
  _QWORD *StackBase; // rax
  __int64 v10; // rbx
  __int64 locked; // rax
  __int64 v12; // rsi
  int v13; // ebx
  unsigned int v14; // ecx
  unsigned __int64 v15; // r14
  __int64 v16; // rdx
  __int64 *v17; // r10
  char v18; // r11
  __int64 v20; // [rsp+30h] [rbp-58h]
  __int128 Src; // [rsp+40h] [rbp-48h] BYREF
  __int64 v22; // [rsp+50h] [rbp-38h]

  v6 = a3;
  Src = 0;
  v22 = 0;
  if ( a2 < 0x18 )
    return 3221225476LL;
  if ( a4 > 0x7FFFFFFEFFFFLL )
    return 3221225485LL;
  if ( a3 )
    RtlCopyFromUser(&Src, a1, 0x18u);
  else
    RtlCopyVolatileMemory(&Src, a1, 0x18u);
  if ( (unsigned int)Src > 1 || DWORD1(Src) )
    return 3221225485LL;
  if ( (_DWORD)Src == 1 )
    return 3221225659LL;
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
    v10 = StackBase[10];
  else
    v10 = 0;
  locked = SkmiObtainLockedVad(v10, a4 >> 12);
  v12 = locked;
  if ( !locked )
    return 3221225632LL;
  if ( (*(_QWORD *)(locked + 48) & 0x700000000000LL) != 0 || !*(_QWORD *)(locked + 56) )
  {
    v13 = -1073741503;
  }
  else
  {
    *((_QWORD *)&Src + 1) = 0;
    v22 = 0;
    if ( (*(_DWORD *)(locked + 68) & 2) != 0 )
    {
      if ( (_DWORD)Src )
      {
        v14 = 0;
        if ( (_DWORD)Src == 1 )
          v14 = dword_140156D74;
      }
      else
      {
        v14 = dword_140156D70;
      }
      v15 = (*(unsigned int *)(locked + 28) | ((unsigned __int64)(*(_DWORD *)(locked + 32) & 0xFFF000) << 20))
          - (((SkmiPatchFlags & 1) != 0 ? SkmiHotPatchAddressReservePages : 0)
           + (unsigned int)((unsigned __int64)qword_140156D80 >> 12))
          + 1
          + ((unsigned __int64)v14 >> 12);
      v20 = v10 + 8;
      SkAcquireSpinLockShared(v10 + 8);
      LOBYTE(v10) = 0;
      if ( (unsigned int)SkmiIsLeafPteValid(8 * (v15 & 0xFFFFFFFFFLL) - 0x98000000000LL) )
        v10 = *v17;
      LOBYTE(v16) = v18;
      RtlpReleasePropStoreLockShared(v20, v16);
      if ( (v10 & 1) != 0 )
      {
        *((_QWORD *)&Src + 1) = (v15 << 12) - a4;
        v22 = 4096;
      }
      v13 = 0;
      v6 = a3;
    }
    else
    {
      v13 = 0;
    }
  }
  SkmiUnlockAndDereferenceVad(v12);
  if ( v13 >= 0 )
  {
    if ( v6 )
      RtlCopyToUser(a1, &Src, 0x18u);
    else
      RtlCopyVolatileMemory(a1, &Src, 0x18u);
    if ( a5 )
      *a5 = 24;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140066b20  mov     [rsp+arg_8], rbx
0x140066b25  mov     [rsp+arg_10], rsi
0x140066b2a  push    rdi
0x140066b2b  push    r12
0x140066b2d  push    r13
0x140066b2f  push    r14
0x140066b31  push    r15
0x140066b33  sub     rsp, 60h
0x140066b37  mov     rax, cs:__security_cookie
0x140066b3e  xor     rax, rsp
0x140066b41  mov     [rsp+88h+var_30], rax
0x140066b46  mov     r13, r9
0x140066b49  mov     r14b, r8b
0x140066b4c  mov     [rsp+88h+var_68], r8b
0x140066b51  mov     r15, rcx
0x140066b54  mov     r12, [rsp+88h+arg_20]
0x140066b5c  mov     [rsp+88h+var_50], r12
0x140066b61  xorps   xmm0, xmm0
0x140066b64  xor     eax, eax
0x140066b66  movups  [rsp+88h+Src], xmm0
0x140066b6b  mov     [rsp+88h+var_38], rax
0x140066b70  lea     edi, [rax+18h]
0x140066b73  cmp     rdx, rdi
0x140066b76  jnb     short loc_140066B82
0x140066b78  mov     eax, 0C0000004h
0x140066b7d  jmp     loc_140066D7C
0x140066b82  mov     rax, 7FFFFFFEFFFFh
0x140066b8c  cmp     r13, rax
0x140066b8f  ja      loc_140066D77
0x140066b95  mov     rdx, r15; Src
0x140066b98  lea     rcx, [rsp+88h+Src]; void *
0x140066b9d  test    r8b, r8b
0x140066ba0  mov     r8, rdi; Size
0x140066ba3  jz      short loc_140066BAC
0x140066ba5  call    RtlCopyFromUser
0x140066baa  jmp     short loc_140066BB2
0x140066bac  call    RtlCopyVolatileMemory
0x140066bb1  nop
0x140066bb2  cmp     dword ptr [rsp+88h+Src], 1
0x140066bb7  ja      loc_140066D77
0x140066bbd  cmp     dword ptr [rsp+88h+Src+4], 0
0x140066bc2  jnz     loc_140066D77
0x140066bc8  cmp     dword ptr [rsp+88h+Src], 1
0x140066bcd  jnz     short loc_140066BD9
0x140066bcf  mov     eax, 0C00000BBh
0x140066bd4  jmp     loc_140066D7C
0x140066bd9  mov     rax, gs:8
0x140066be2  test    rax, rax
0x140066be5  jz      short loc_140066BED
0x140066be7  mov     rbx, [rax+50h]
0x140066beb  jmp     short loc_140066BEF
0x140066bed  xor     ebx, ebx
0x140066bef  mov     rdx, r13
0x140066bf2  shr     rdx, 0Ch
0x140066bf6  mov     rcx, rbx
0x140066bf9  call    SkmiObtainLockedVad
0x140066bfe  mov     rsi, rax
0x140066c01  test    rax, rax
0x140066c04  jnz     short loc_140066C10
0x140066c06  mov     eax, 0C00000A0h
0x140066c0b  jmp     loc_140066D7C
0x140066c10  mov     rcx, 700000000000h
0x140066c1a  test    [rax+30h], rcx
0x140066c1e  jnz     loc_140066D2D
0x140066c24  cmp     qword ptr [rax+38h], 0
0x140066c29  jz      loc_140066D2D
0x140066c2f  mov     qword ptr [rsp+88h+Src+8], 0
0x140066c38  mov     [rsp+88h+var_38], 0
0x140066c41  mov     eax, [rax+44h]
0x140066c44  test    al, 2
0x140066c46  jnz     short loc_140066C4F
0x140066c48  xor     ebx, ebx
0x140066c4a  jmp     loc_140066D32
0x140066c4f  mov     al, byte ptr cs:SkmiPatchFlags
0x140066c55  and     al, 1
0x140066c57  neg     al
0x140066c59  sbb     ecx, ecx
0x140066c5b  and     ecx, cs:SkmiHotPatchAddressReservePages
0x140066c61  mov     edx, [rsi+20h]
0x140066c64  and     edx, 0FFF000h
0x140066c6a  shl     rdx, 14h
0x140066c6e  mov     eax, [rsi+1Ch]
0x140066c71  or      rdx, rax
0x140066c74  mov     rax, cs:qword_140156D80
0x140066c7b  shr     rax, 0Ch
0x140066c7f  add     eax, ecx
0x140066c81  sub     rdx, rax
0x140066c84  mov     r8, qword ptr [rsp+88h+Src]
0x140066c89  test    r8d, r8d
0x140066c8c  jnz     short loc_140066C96
0x140066c8e  mov     ecx, cs:dword_140156D70
0x140066c94  jmp     short loc_140066CA3
0x140066c96  xor     ecx, ecx
0x140066c98  cmp     r8d, 1
0x140066c9c  cmovz   ecx, cs:dword_140156D74
0x140066ca3  mov     r14d, ecx
0x140066ca6  shr     r14, 0Ch
0x140066caa  inc     rdx
0x140066cad  add     r14, rdx
0x140066cb0  mov     rax, r14
0x140066cb3  mov     rcx, 0FFFFFFFFFh
0x140066cbd  and     rax, rcx
0x140066cc0  mov     rcx, 0FFFFF68000000000h
0x140066cca  lea     rax, [rcx+rax*8]
0x140066cce  mov     [rsp+88h+var_60], rax
0x140066cd3  lea     rax, [rbx+8]
0x140066cd7  mov     [rsp+88h+var_58], rax
0x140066cdc  mov     rcx, rax
0x140066cdf  call    SkAcquireSpinLockShared
0x140066ce4  mov     r11b, al
0x140066ce7  xor     ebx, ebx
0x140066ce9  mov     r10, [rsp+88h+var_60]
0x140066cee  mov     rcx, r10
0x140066cf1  call    SkmiIsLeafPteValid
0x140066cf6  test    eax, eax
0x140066cf8  jz      short loc_140066CFD
0x140066cfa  mov     rbx, [r10]
0x140066cfd  mov     dl, r11b
0x140066d00  mov     rcx, [rsp+88h+var_58]
0x140066d05  call    RtlpReleasePropStoreLockShared
0x140066d0a  test    bl, 1
0x140066d0d  jz      short loc_140066D24
0x140066d0f  shl     r14, 0Ch
0x140066d13  sub     r14, r13
0x140066d16  mov     qword ptr [rsp+88h+Src+8], r14
0x140066d1b  mov     [rsp+88h+var_38], 1000h
0x140066d24  xor     ebx, ebx
0x140066d26  mov     r14b, [rsp+88h+var_68]
0x140066d2b  jmp     short loc_140066D32
0x140066d2d  mov     ebx, 0C0000141h
0x140066d32  mov     rcx, rsi
0x140066d35  call    SkmiUnlockAndDereferenceVad
0x140066d3a  test    ebx, ebx
0x140066d3c  js      short loc_140066D71
0x140066d3e  mov     r8, rdi; Size
0x140066d41  lea     rdx, [rsp+88h+Src]; Src
0x140066d46  mov     rcx, r15; void *
0x140066d49  test    r14b, r14b
0x140066d4c  jz      short loc_140066D55
0x140066d4e  call    RtlCopyToUser
0x140066d53  jmp     short loc_140066D5A
0x140066d55  call    RtlCopyVolatileMemory
0x140066d5a  jmp     short loc_140066D68
0x140066d5c  mov     ebx, eax
0x140066d5e  mov     edi, 18h
0x140066d63  mov     r12, [rsp+88h+var_50]
0x140066d68  test    r12, r12
0x140066d6b  jz      short loc_140066D71
0x140066d6d  mov     [r12], rdi
0x140066d71  mov     eax, ebx
0x140066d73  jmp     short loc_140066D7C
0x140066d75  jmp     short loc_140066D7C
0x140066d77  mov     eax, 0C000000Dh
0x140066d7c  mov     rcx, [rsp+88h+var_30]
0x140066d81  xor     rcx, rsp; StackCookie
0x140066d84  call    __security_check_cookie
0x140066d89  lea     r11, [rsp+88h+var_28]
0x140066d8e  mov     rbx, [r11+38h]
0x140066d92  mov     rsi, [r11+40h]
0x140066d96  mov     rsp, r11
0x140066d99  pop     r15
0x140066d9b  pop     r14
0x140066d9d  pop     r13
0x140066d9f  pop     r12
0x140066da1  pop     rdi
0x140066da2  retn
```

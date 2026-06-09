# WimSqmAddToStreamEx

- ea: `0x140010954`
- end: `0x140010b66`
- name: `WimSqmAddToStreamEx`
- size: `530`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400108c0`

## callees

- `0x140010954`
- `0x140011560`
- `0x1400119c0`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x1400109b1`
- `ntoskrnl!EtwEventEnabled` at `0x1400109b1`
- `ntoskrnl!EtwWrite` at `0x140010b38`
- `ntoskrnl!EtwWrite` at `0x140010b38`

## pseudocode

```c
char __fastcall WimSqmAddToStreamEx(int a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  unsigned int v5; // r8d
  ULONG v6; // r9d
  unsigned int i; // r10d
  int *v8; // rdx
  unsigned int v9; // r10d
  int *v10; // r9
  ULONG v12; // [rsp+38h] [rbp-69h] BYREF
  unsigned int v13; // [rsp+40h] [rbp-61h] BYREF
  int v14; // [rsp+48h] [rbp-59h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData[7]; // [rsp+58h] [rbp-49h] BYREF
  _BYTE v16[32]; // [rsp+C8h] [rbp+27h] BYREF
  int v17; // [rsp+108h] [rbp+67h] BYREF

  v17 = a1;
  v14 = 0;
  v13 = 1;
  memset(UserData, 0, sizeof(UserData));
  v12 = 0;
  LOBYTE(v4) = EtwEventEnabled(WimSqmProvider, &SQM_ADD_STREAMROW);
  if ( !(_BYTE)v4 )
    return v4;
  v5 = v13;
  v6 = v12;
  for ( i = 0; i < v13; ++i )
  {
    if ( *(_DWORD *)(a3 + 16LL * i + 4) == 1 )
      goto LABEL_7;
    if ( *(_DWORD *)(a3 + 16LL * i + 4) != 2 )
    {
      if ( *(_DWORD *)(a3 + 16LL * i + 4) != 3 )
        return v4;
LABEL_7:
      v4 = 16;
      goto LABEL_8;
    }
    v4 = 8;
LABEL_8:
    v6 += v4;
    v12 = v6;
  }
  if ( v6 <= 0x20 )
  {
    *(_QWORD *)&UserData[0].Size = 16;
    UserData[0].Ptr = (ULONGLONG)WinSqmGlobalSession;
    v8 = (int *)v16;
    *(_QWORD *)&UserData[1].Size = 4;
    UserData[1].Ptr = (ULONGLONG)&v17;
    v9 = 0;
    *(_QWORD *)&UserData[2].Size = 4;
    UserData[2].Ptr = (ULONGLONG)s_dwProcessHashValue;
    UserData[3].Ptr = (ULONGLONG)&v13;
    UserData[4].Ptr = (ULONGLONG)&v12;
    *(_QWORD *)&UserData[3].Size = 4;
    *(_QWORD *)&UserData[4].Size = 4;
    while ( v9 < v5 )
    {
      v4 = *(_DWORD *)(a3 + 16LL * v9 + 4);
      *v8 = v4;
      if ( *(_DWORD *)(a3 + 16LL * v9 + 4) == 1 )
      {
        LOBYTE(v4) = v12;
        v10 = v8 + 4;
        if ( v8 + 4 > (int *)&v16[v12] )
          return v4;
        v8[2] = *(_DWORD *)(a3 + 16LL * v9 + 8);
      }
      else
      {
        if ( *(_DWORD *)(a3 + 16LL * v9 + 4) != 3 )
          return v4;
        LOBYTE(v4) = v12;
        v10 = v8 + 4;
        if ( v8 + 4 > (int *)&v16[v12] )
          return v4;
        *((_QWORD *)v8 + 1) = *(_QWORD *)(a3 + 16LL * v9 + 8);
      }
      v8[1] = 16;
      ++v9;
      v5 = v13;
      v8 = v10;
      v6 = v12;
    }
    UserData[5].Ptr = (ULONGLONG)v16;
    UserData[5].Size = v6;
    UserData[6].Ptr = (ULONGLONG)&v14;
    UserData[5].Reserved = 0;
    *(_QWORD *)&UserData[6].Size = 4;
    LOBYTE(v4) = EtwWrite(WimSqmProvider, &SQM_ADD_STREAMROW, 0, 7u, UserData);
  }
  return v4;
}

```

## disassembly

```asm
0x140010954  mov     rax, rsp
0x140010957  mov     [rax+10h], rbx
0x14001095b  mov     [rax+18h], rsi
0x14001095f  mov     [rax+8], ecx
0x140010962  push    rbp
0x140010963  lea     rbp, [rax-5Fh]
0x140010967  sub     rsp, 0F0h
0x14001096e  mov     rax, cs:__security_cookie
0x140010975  xor     rax, rsp
0x140010978  mov     [rbp+57h+var_10], rax
0x14001097c  xor     edx, edx; Val
0x14001097e  mov     [rbp+57h+var_B0], 0
0x140010985  mov     rbx, r8
0x140010988  mov     [rbp+57h+var_B8], 1
0x14001098f  lea     rcx, [rbp+57h+var_A0]; void *
0x140010993  lea     r8d, [rdx+70h]; Size
0x140010997  call    memset
0x14001099c  mov     rcx, cs:WimSqmProvider; RegHandle
0x1400109a3  lea     rdx, SQM_ADD_STREAMROW; EventDescriptor
0x1400109aa  mov     [rbp+57h+var_C0], 0
0x1400109b1  call    cs:__imp_EtwEventEnabled
0x1400109b8  nop     dword ptr [rax+rax+00h]
0x1400109bd  test    al, al
0x1400109bf  jz      loc_140010B44
0x1400109c5  mov     r8d, [rbp+57h+var_B8]
0x1400109c9  cmp     r8d, 40h ; '@'
0x1400109cd  jbe     short loc_1400109D9
0x1400109cf  mov     r8d, 40h ; '@'
0x1400109d5  mov     [rbp+57h+var_B8], r8d
0x1400109d9  mov     r9d, [rbp+57h+var_C0]
0x1400109dd  xor     r10d, r10d
0x1400109e0  lea     r11d, [r10+10h]
0x1400109e4  cmp     r10d, r8d
0x1400109e7  jnb     short loc_140010A1C
0x1400109e9  mov     ecx, r10d
0x1400109ec  add     rcx, rcx
0x1400109ef  mov     edx, [rbx+rcx*8+4]
0x1400109f3  sub     edx, 1
0x1400109f6  jz      short loc_140010A06
0x1400109f8  sub     edx, 1
0x1400109fb  jz      short loc_140010A15
0x1400109fd  cmp     edx, 1
0x140010a00  jnz     loc_140010B44
0x140010a06  mov     eax, r11d
0x140010a09  add     r9d, eax
0x140010a0c  mov     [rbp+57h+var_C0], r9d
0x140010a10  inc     r10d
0x140010a13  jmp     short loc_1400109E4
0x140010a15  mov     eax, 8
0x140010a1a  jmp     short loc_140010A09
0x140010a1c  cmp     r9d, 20h ; ' '
0x140010a20  ja      loc_140010B44
0x140010a26  lea     rax, WinSqmGlobalSession
0x140010a2d  mov     qword ptr [rbp+57h+var_A0.Size], r11
0x140010a31  mov     [rbp+57h+var_A0.Ptr], rax
0x140010a35  lea     rdx, [rbp+57h+var_30]
0x140010a39  lea     rax, [rbp+57h+arg_0]
0x140010a3d  mov     [rbp+57h+var_88], 4
0x140010a45  mov     [rbp+57h+var_90], rax
0x140010a49  xor     r10d, r10d
0x140010a4c  lea     rax, s_dwProcessHashValue
0x140010a53  mov     [rbp+57h+var_78], 4
0x140010a5b  mov     [rbp+57h+var_80], rax
0x140010a5f  lea     rax, [rbp+57h+var_B8]
0x140010a63  mov     [rbp+57h+var_70], rax
0x140010a67  lea     rax, [rbp+57h+var_C0]
0x140010a6b  mov     [rbp+57h+var_60], rax
0x140010a6f  mov     [rbp+57h+var_68], 4
0x140010a77  mov     [rbp+57h+var_58], 4
0x140010a7f  cmp     r10d, r8d
0x140010a82  jnb     short loc_140010AF5
0x140010a84  mov     r8d, r10d
0x140010a87  add     r8, r8
0x140010a8a  mov     eax, [rbx+r8*8+4]
0x140010a8f  mov     [rdx], eax
0x140010a91  mov     ecx, [rbx+r8*8+4]
0x140010a96  sub     ecx, 1
0x140010a99  jz      short loc_140010AC6
0x140010a9b  cmp     ecx, 2
0x140010a9e  jnz     loc_140010B44
0x140010aa4  mov     eax, [rbp+57h+var_C0]
0x140010aa7  lea     rcx, [rbp+57h+var_30]
0x140010aab  add     rcx, rax
0x140010aae  lea     r9, [rdx+10h]
0x140010ab2  cmp     r9, rcx
0x140010ab5  ja      loc_140010B44
0x140010abb  mov     rax, [rbx+r8*8+8]
0x140010ac0  mov     [rdx+8], rax
0x140010ac4  jmp     short loc_140010AE1
0x140010ac6  mov     eax, [rbp+57h+var_C0]
0x140010ac9  lea     rcx, [rbp+57h+var_30]
0x140010acd  add     rcx, rax
0x140010ad0  lea     r9, [rdx+10h]
0x140010ad4  cmp     r9, rcx
0x140010ad7  ja      short loc_140010B44
0x140010ad9  mov     eax, [rbx+r8*8+8]
0x140010ade  mov     [rdx+8], eax
0x140010ae1  mov     [rdx+4], r11d
0x140010ae5  inc     r10d
0x140010ae8  mov     r8d, [rbp+57h+var_B8]
0x140010aec  mov     rdx, r9
0x140010aef  mov     r9d, [rbp+57h+var_C0]
0x140010af3  jmp     short loc_140010A7F
0x140010af5  mov     rcx, cs:WimSqmProvider; RegHandle
0x140010afc  lea     rax, [rbp+57h+var_30]
0x140010b00  mov     [rbp+57h+var_50], rax
0x140010b04  lea     rdx, SQM_ADD_STREAMROW; EventDescriptor
0x140010b0b  lea     rax, [rbp+57h+var_B0]
0x140010b0f  mov     [rbp+57h+var_48], r9d
0x140010b13  mov     [rbp+57h+var_40], rax
0x140010b17  mov     r9d, 7; UserDataCount
0x140010b1d  lea     rax, [rbp+57h+var_A0]
0x140010b21  mov     [rbp+57h+var_44], 0
0x140010b28  xor     r8d, r8d; ActivityId
0x140010b2b  mov     [rsp+0F0h+UserData], rax; UserData
0x140010b30  mov     [rbp+57h+var_38], 4
0x140010b38  call    cs:__imp_EtwWrite
0x140010b3f  nop     dword ptr [rax+rax+00h]
0x140010b44  mov     rcx, [rbp+57h+var_10]
0x140010b48  xor     rcx, rsp; StackCookie
0x140010b4b  call    __security_check_cookie
0x140010b50  lea     r11, [rsp+0F0h+var_s0]
0x140010b58  mov     rbx, [r11+18h]
0x140010b5c  mov     rsi, [r11+20h]
0x140010b60  mov     rsp, r11
0x140010b63  pop     rbp
0x140010b64  retn
```

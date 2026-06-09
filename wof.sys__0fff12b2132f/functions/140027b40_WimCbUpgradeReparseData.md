# WimCbUpgradeReparseData

- ea: `0x140027b40`
- end: `0x140027c9f`
- name: `WimCbUpgradeReparseData`
- size: `351`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path`

## callees

- `0x140027b40`
- `0x14002d5f4`
- `0x14002e4f0`
- `0x14003c3fc`
- `0x14003c4c8`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x140027c6f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140027c6f`

## pseudocode

```c
__int64 __fastcall WimCbUpgradeReparseData(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5,
        __int64 a6,
        _DWORD *a7)
{
  int v7; // ebx
  __int64 v11; // rsi
  __int64 v13; // rdi
  _QWORD *v14; // r15
  __int64 v15; // rax
  __int64 v16; // [rsp+68h] [rbp+10h] BYREF

  v7 = 0;
  v16 = 0;
  if ( *(_DWORD *)a3 == 1 )
  {
    if ( a5 )
      *a5 = 1;
    v11 = a6;
    if ( a6 )
    {
      if ( *a7 < 0x50u )
        return 3221225507LL;
      v7 = WimFSFFindOverlayByDataSource(a2, *(_QWORD *)(a3 + 8), &v16);
      if ( v7 < 0 )
        return 3221226606LL;
      v13 = v16;
      if ( !(unsigned __int8)WimFSFAcquireRundownAndRemount(a1, a2, v16) )
        return 3221226606LL;
      v14 = (_QWORD *)WimFSFFindStreamResource(a1, v13, (unsigned int *)(a3 + 16));
      if ( v14 )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v13 + 104) + 100LL) & 8) != 0 || (v7 = WimFSFLoadOffsetTableHash(a1), v7 >= 0) )
        {
          *(_OWORD *)v11 = *(_OWORD *)a3;
          *(_OWORD *)(v11 + 16) = *(_OWORD *)(a3 + 16);
          *(_QWORD *)(v11 + 32) = *(_QWORD *)(a3 + 32);
          v15 = *(_QWORD *)(v13 + 104);
          *(_OWORD *)(v11 + 36) = *(_OWORD *)(v15 + 946);
          *(_DWORD *)(v11 + 52) = *(_DWORD *)(v15 + 962);
          *(_DWORD *)v11 = 2;
          *(_QWORD *)(v11 + 56) = v14[2];
          *(_QWORD *)(v11 + 64) = *v14 & 0xFFFFFFFFFFFFFFLL;
          *(_QWORD *)(v11 + 72) = v14[1];
        }
      }
      else
      {
        v7 = -1073741275;
      }
      ExReleaseRundownProtection(*(PEX_RUNDOWN_REF *)(v13 + 96));
    }
    else if ( a7 )
    {
      *a7 = 80;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140027b40  push    rbx
0x140027b42  push    rbp
0x140027b43  push    rsi
0x140027b44  push    rdi
0x140027b45  push    r14
0x140027b47  push    r15
0x140027b49  sub     rsp, 28h
0x140027b4d  xor     ebx, ebx
0x140027b4f  mov     [rsp+58h+arg_8], 0
0x140027b58  cmp     dword ptr [r8], 1
0x140027b5c  mov     rbp, r8
0x140027b5f  mov     r15, rdx
0x140027b62  mov     r14, rcx
0x140027b65  jnz     loc_140027C8F
0x140027b6b  mov     rax, [rsp+58h+arg_20]
0x140027b73  test    rax, rax
0x140027b76  jz      short loc_140027B7B
0x140027b78  mov     byte ptr [rax], 1
0x140027b7b  mov     rsi, [rsp+58h+arg_28]
0x140027b83  mov     rax, [rsp+58h+arg_30]
0x140027b8b  test    rsi, rsi
0x140027b8e  jz      loc_140027C84
0x140027b94  cmp     dword ptr [rax], 50h ; 'P'
0x140027b97  jnb     short loc_140027BA3
0x140027b99  mov     eax, 0C0000023h
0x140027b9e  jmp     loc_140027C91
0x140027ba3  mov     rdx, [rbp+8]
0x140027ba7  lea     r8, [rsp+58h+arg_8]
0x140027bac  mov     rcx, r15
0x140027baf  call    WimFSFFindOverlayByDataSource
0x140027bb4  mov     ebx, eax
0x140027bb6  test    eax, eax
0x140027bb8  js      loc_140027C7D
0x140027bbe  mov     rdi, [rsp+58h+arg_8]
0x140027bc3  mov     rdx, r15
0x140027bc6  mov     r8, rdi
0x140027bc9  mov     rcx, r14
0x140027bcc  call    WimFSFAcquireRundownAndRemount
0x140027bd1  test    al, al
0x140027bd3  jz      loc_140027C7D
0x140027bd9  lea     r8, [rbp+10h]
0x140027bdd  mov     rdx, rdi
0x140027be0  mov     rcx, r14
0x140027be3  call    WimFSFFindStreamResource
0x140027be8  mov     r15, rax
0x140027beb  test    rax, rax
0x140027bee  jnz     short loc_140027BF7
0x140027bf0  mov     ebx, 0C0000225h
0x140027bf5  jmp     short loc_140027C6B
0x140027bf7  mov     rdx, [rdi+68h]
0x140027bfb  mov     eax, [rdx+64h]
0x140027bfe  test    al, 8
0x140027c00  jnz     short loc_140027C10
0x140027c02  mov     rcx, r14
0x140027c05  call    WimFSFLoadOffsetTableHash
0x140027c0a  mov     ebx, eax
0x140027c0c  test    eax, eax
0x140027c0e  js      short loc_140027C6B
0x140027c10  movups  xmm0, xmmword ptr [rbp+0]
0x140027c14  mov     rcx, 0FFFFFFFFFFFFFFh
0x140027c1e  movups  xmmword ptr [rsi], xmm0
0x140027c21  movups  xmm1, xmmword ptr [rbp+10h]
0x140027c25  movups  xmmword ptr [rsi+10h], xmm1
0x140027c29  movsd   xmm0, qword ptr [rbp+20h]
0x140027c2e  movsd   qword ptr [rsi+20h], xmm0
0x140027c33  mov     rax, [rdi+68h]
0x140027c37  movups  xmm0, xmmword ptr [rax+3B2h]
0x140027c3e  movups  xmmword ptr [rsi+24h], xmm0
0x140027c42  mov     eax, [rax+3C2h]
0x140027c48  mov     [rsi+34h], eax
0x140027c4b  mov     dword ptr [rsi], 2
0x140027c51  mov     rax, [r15+10h]
0x140027c55  mov     [rsi+38h], rax
0x140027c59  mov     rax, [r15]
0x140027c5c  and     rax, rcx
0x140027c5f  mov     [rsi+40h], rax
0x140027c63  mov     rax, [r15+8]
0x140027c67  mov     [rsi+48h], rax
0x140027c6b  mov     rcx, [rdi+60h]; RunRef
0x140027c6f  call    cs:__imp_ExReleaseRundownProtection
0x140027c76  nop     dword ptr [rax+rax+00h]
0x140027c7b  jmp     short loc_140027C8F
0x140027c7d  mov     eax, 0C000046Eh
0x140027c82  jmp     short loc_140027C91
0x140027c84  test    rax, rax
0x140027c87  jz      short loc_140027C8F
0x140027c89  mov     dword ptr [rax], 50h ; 'P'
0x140027c8f  mov     eax, ebx
0x140027c91  add     rsp, 28h
0x140027c95  pop     r15
0x140027c97  pop     r14
0x140027c99  pop     rdi
0x140027c9a  pop     rsi
0x140027c9b  pop     rbp
0x140027c9c  pop     rbx
0x140027c9d  retn
```

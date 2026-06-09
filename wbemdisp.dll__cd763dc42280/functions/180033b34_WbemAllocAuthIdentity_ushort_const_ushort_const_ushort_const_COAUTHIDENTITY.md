# WbemAllocAuthIdentity(ushort const *,ushort const *,ushort const *,_COAUTHIDENTITY * *)

- ea: `0x180033b34`
- end: `0x180033d62`
- name: `?WbemAllocAuthIdentity@@YAJPEBG00PEAPEAU_COAUTHIDENTITY@@@Z`
- size: `558`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _COAUTHIDENTITY **)`
- caller_count: `5`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008de0`
- `0x18000a7b0`
- `0x18000b0ac`
- `0x18001cc78`
- `0x18001e5dc`

## callees

- `0x180018460`
- `0x1800338fc`
- `0x180033924`
- `0x18003394c`
- `0x180033980`
- `0x180033a6c`
- `0x180033b34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033b69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033bd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033c4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033cc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033b69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033bd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033c4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033cc7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WbemAllocAuthIdentity(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _COAUTHIDENTITY **a4)
{
  _OWORD *v8; // rbx
  unsigned __int16 *v9; // r15
  __int64 v10; // rdi
  __int64 v11; // rdx
  int *v12; // rax
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // r14
  __int64 v15; // rdx
  int *v16; // rax
  unsigned __int16 *v17; // rax
  unsigned __int16 *v18; // rsi
  int *v19; // rax
  unsigned __int16 *v20; // rax
  unsigned int v21; // ebx
  int v22; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v23[4]; // [rsp+24h] [rbp-54h] BYREF
  _OWORD *v24; // [rsp+28h] [rbp-50h] BYREF
  char v25; // [rsp+30h] [rbp-48h]
  unsigned __int16 *v26; // [rsp+38h] [rbp-40h] BYREF
  char v27; // [rsp+40h] [rbp-38h]
  unsigned __int16 *v28; // [rsp+48h] [rbp-30h] BYREF
  char v29; // [rsp+50h] [rbp-28h]
  unsigned __int16 *v30; // [rsp+58h] [rbp-20h] BYREF
  char v31; // [rsp+60h] [rbp-18h]

  if ( !a4 )
    return 2147749896LL;
  v8 = CoTaskMemAlloc(0x30u);
  if ( !v8 )
    return 2147749894LL;
  v24 = v8;
  v25 = 0;
  *v8 = 0;
  v8[1] = 0;
  v8[2] = 0;
  v9 = 0;
  v22 = 0;
  v10 = -1;
  if ( a1 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a1[v11] );
    SafeInt<int>::operator=<unsigned __int64>(&v22);
    SafeInt<int>::operator+=<int>(&v22);
    v12 = (int *)SafeInt<int>::operator*<unsigned __int64>(&v22, v23);
    v13 = (unsigned __int16 *)CoTaskMemAlloc(*v12);
    v9 = v13;
    if ( !v13 )
      goto LABEL_9;
    StringCchCopyW(v13, v22, a1);
    SafeInt<int>::operator-=<int>(&v22);
    *((_DWORD *)v8 + 2) = v22;
  }
  v14 = 0;
  v26 = v9;
  v27 = 0;
  if ( a3 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a3[v15] );
    SafeInt<int>::operator=<unsigned __int64>(&v22);
    SafeInt<int>::operator+=<int>(&v22);
    v16 = (int *)SafeInt<int>::operator*<unsigned __int64>(&v22, v23);
    v17 = (unsigned __int16 *)CoTaskMemAlloc(*v16);
    v14 = v17;
    if ( !v17 )
    {
      OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>(&v26);
LABEL_9:
      OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>(&v24);
      return 2147749894LL;
    }
    StringCchCopyW(v17, v22, a3);
    SafeInt<int>::operator-=<int>(&v22);
    *((_DWORD *)v8 + 6) = v22;
  }
  v18 = 0;
  v28 = v14;
  v29 = 0;
  if ( !a2 )
    goto LABEL_22;
  do
    ++v10;
  while ( a2[v10] );
  SafeInt<int>::operator=<unsigned __int64>(&v22);
  SafeInt<int>::operator+=<int>(&v22);
  v19 = (int *)SafeInt<int>::operator*<unsigned __int64>(&v22, v23);
  v20 = (unsigned __int16 *)CoTaskMemAlloc(*v19);
  v18 = v20;
  if ( v20 )
  {
    StringCchCopyW(v20, v22, a2);
    SafeInt<int>::operator-=<int>(&v22);
    *((_DWORD *)v8 + 10) = v22;
LABEL_22:
    v30 = v18;
    v27 = 1;
    *(_QWORD *)v8 = v9;
    v29 = 1;
    *((_QWORD *)v8 + 2) = v14;
    v31 = 1;
    *((_QWORD *)v8 + 4) = v18;
    *((_DWORD *)v8 + 11) = 2;
    v25 = 1;
    *a4 = (struct _COAUTHIDENTITY *)v8;
    OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>(&v30);
    v21 = 0;
    goto LABEL_23;
  }
  v21 = -2147217402;
LABEL_23:
  OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>(&v28);
  OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>(&v26);
  OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&void CoTaskMemFree(void *)>(&v24);
  return v21;
}

```

## disassembly

```asm
0x180033b34  mov     [rsp-40h+arg_18], r9
0x180033b39  push    rbp
0x180033b3a  push    rbx
0x180033b3b  push    rsi
0x180033b3c  push    rdi
0x180033b3d  push    r12
0x180033b3f  push    r13
0x180033b41  push    r14
0x180033b43  push    r15
0x180033b45  mov     rbp, rsp
0x180033b48  sub     rsp, 78h
0x180033b4c  mov     r12, r8
0x180033b4f  mov     r13, rdx
0x180033b52  mov     rsi, rcx
0x180033b55  test    r9, r9
0x180033b58  jnz     short loc_180033B64
0x180033b5a  mov     eax, 80041008h
0x180033b5f  jmp     loc_180033D51
0x180033b64  mov     ecx, 30h ; '0'; cb
0x180033b69  call    cs:__imp_CoTaskMemAlloc
0x180033b6f  mov     rbx, rax
0x180033b72  xor     eax, eax
0x180033b74  test    rbx, rbx
0x180033b77  jnz     short loc_180033B83
0x180033b79  mov     eax, 80041006h
0x180033b7e  jmp     loc_180033D51
0x180033b83  mov     [rbp+var_50], rbx
0x180033b87  mov     [rbp+var_48], al
0x180033b8a  xorps   xmm0, xmm0
0x180033b8d  movups  xmmword ptr [rbx], xmm0
0x180033b90  movups  xmmword ptr [rbx+10h], xmm0
0x180033b94  movups  xmmword ptr [rbx+20h], xmm0
0x180033b98  mov     r15, rax
0x180033b9b  mov     [rbp+var_58], eax
0x180033b9e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180033ba2  test    rsi, rsi
0x180033ba5  jz      short loc_180033C0E
0x180033ba7  mov     rdx, rdi
0x180033baa  inc     rdx
0x180033bad  cmp     [rsi+rdx*2], ax
0x180033bb1  jnz     short loc_180033BAA
0x180033bb3  lea     rcx, [rbp+var_58]
0x180033bb7  call    ??$?4_K@?$SafeInt@H@@QEAAAEAV0@_K@Z; SafeInt<int>::operator=<unsigned __int64>(unsigned __int64)
0x180033bbc  lea     rcx, [rbp+var_58]
0x180033bc0  call    ??$?YH@?$SafeInt@H@@QEAAAEAV0@H@Z; SafeInt<int>::operator+=<int>(int)
0x180033bc5  lea     rdx, [rbp+var_54]
0x180033bc9  lea     rcx, [rbp+var_58]
0x180033bcd  call    ??$?D_K@?$SafeInt@H@@QEAA?AV0@_K@Z; SafeInt<int>::operator*<unsigned __int64>(unsigned __int64)
0x180033bd2  movsxd  rcx, dword ptr [rax]; cb
0x180033bd5  call    cs:__imp_CoTaskMemAlloc
0x180033bdb  mov     r15, rax
0x180033bde  test    rax, rax
0x180033be1  jnz     short loc_180033BEE
0x180033be3  lea     rcx, [rbp+var_50]
0x180033be7  call    ??1?$OnDeleteIf@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@QEAA@XZ; OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>(void)
0x180033bec  jmp     short loc_180033B79
0x180033bee  movsxd  rdx, [rbp+var_58]; unsigned __int64
0x180033bf2  mov     r8, rsi; unsigned __int16 *
0x180033bf5  mov     rcx, rax; unsigned __int16 *
0x180033bf8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033bfd  lea     rcx, [rbp+var_58]
0x180033c01  call    ??$?ZH@?$SafeInt@H@@QEAAAEAV0@H@Z; SafeInt<int>::operator-=<int>(int)
0x180033c06  mov     eax, [rbp+var_58]
0x180033c09  mov     [rbx+8], eax
0x180033c0c  xor     eax, eax
0x180033c0e  mov     r14, rax
0x180033c11  mov     [rbp+var_40], r15
0x180033c15  mov     [rbp+var_38], al
0x180033c18  test    r12, r12
0x180033c1b  jz      short loc_180033C88
0x180033c1d  mov     rdx, rdi
0x180033c20  inc     rdx
0x180033c23  cmp     [r12+rdx*2], ax
0x180033c28  jnz     short loc_180033C20
0x180033c2a  lea     rcx, [rbp+var_58]
0x180033c2e  call    ??$?4_K@?$SafeInt@H@@QEAAAEAV0@_K@Z; SafeInt<int>::operator=<unsigned __int64>(unsigned __int64)
0x180033c33  lea     rcx, [rbp+var_58]
0x180033c37  call    ??$?YH@?$SafeInt@H@@QEAAAEAV0@H@Z; SafeInt<int>::operator+=<int>(int)
0x180033c3c  lea     rdx, [rbp+var_54]
0x180033c40  lea     rcx, [rbp+var_58]
0x180033c44  call    ??$?D_K@?$SafeInt@H@@QEAA?AV0@_K@Z; SafeInt<int>::operator*<unsigned __int64>(unsigned __int64)
0x180033c49  movsxd  rcx, dword ptr [rax]; cb
0x180033c4c  call    cs:__imp_CoTaskMemAlloc
0x180033c52  mov     r14, rax
0x180033c55  test    rax, rax
0x180033c58  jnz     short loc_180033C68
0x180033c5a  lea     rcx, [rbp+var_40]
0x180033c5e  call    ??1?$OnDeleteIf@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@QEAA@XZ; OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>(void)
0x180033c63  jmp     loc_180033BE3
0x180033c68  movsxd  rdx, [rbp+var_58]; unsigned __int64
0x180033c6c  mov     r8, r12; unsigned __int16 *
0x180033c6f  mov     rcx, rax; unsigned __int16 *
0x180033c72  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033c77  lea     rcx, [rbp+var_58]
0x180033c7b  call    ??$?ZH@?$SafeInt@H@@QEAAAEAV0@H@Z; SafeInt<int>::operator-=<int>(int)
0x180033c80  mov     eax, [rbp+var_58]
0x180033c83  mov     [rbx+18h], eax
0x180033c86  xor     eax, eax
0x180033c88  mov     rsi, rax
0x180033c8b  mov     [rbp+var_30], r14
0x180033c8f  mov     [rbp+var_28], al
0x180033c92  test    r13, r13
0x180033c95  jz      short loc_180033CFA
0x180033c97  inc     rdi
0x180033c9a  cmp     [r13+rdi*2+0], ax
0x180033ca0  jnz     short loc_180033C97
0x180033ca2  mov     rdx, rdi
0x180033ca5  lea     rcx, [rbp+var_58]
0x180033ca9  call    ??$?4_K@?$SafeInt@H@@QEAAAEAV0@_K@Z; SafeInt<int>::operator=<unsigned __int64>(unsigned __int64)
0x180033cae  lea     rcx, [rbp+var_58]
0x180033cb2  call    ??$?YH@?$SafeInt@H@@QEAAAEAV0@H@Z; SafeInt<int>::operator+=<int>(int)
0x180033cb7  lea     rdx, [rbp+var_54]
0x180033cbb  lea     rcx, [rbp+var_58]
0x180033cbf  call    ??$?D_K@?$SafeInt@H@@QEAA?AV0@_K@Z; SafeInt<int>::operator*<unsigned __int64>(unsigned __int64)
0x180033cc4  movsxd  rcx, dword ptr [rax]; cb
0x180033cc7  call    cs:__imp_CoTaskMemAlloc
0x180033ccd  mov     rsi, rax
0x180033cd0  test    rax, rax
0x180033cd3  jnz     short loc_180033CDC
0x180033cd5  mov     ebx, 80041006h
0x180033cda  jmp     short loc_180033D32
0x180033cdc  movsxd  rdx, [rbp+var_58]; unsigned __int64
0x180033ce0  mov     r8, r13; unsigned __int16 *
0x180033ce3  mov     rcx, rax; unsigned __int16 *
0x180033ce6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033ceb  lea     rcx, [rbp+var_58]
0x180033cef  call    ??$?ZH@?$SafeInt@H@@QEAAAEAV0@H@Z; SafeInt<int>::operator-=<int>(int)
0x180033cf4  mov     eax, [rbp+var_58]
0x180033cf7  mov     [rbx+28h], eax
0x180033cfa  mov     [rbp+var_20], rsi
0x180033cfe  mov     [rbp+var_38], 1
0x180033d02  mov     [rbx], r15
0x180033d05  mov     [rbp+var_28], 1
0x180033d09  mov     [rbx+10h], r14
0x180033d0d  mov     [rbp+var_18], 1
0x180033d11  mov     [rbx+20h], rsi
0x180033d15  mov     dword ptr [rbx+2Ch], 2
0x180033d1c  mov     [rbp+var_48], 1
0x180033d20  mov     rax, [rbp+arg_18]
0x180033d24  mov     [rax], rbx
0x180033d27  lea     rcx, [rbp+var_20]
0x180033d2b  call    ??1?$OnDeleteIf@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@QEAA@XZ; OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>(void)
0x180033d30  xor     ebx, ebx
0x180033d32  lea     rcx, [rbp+var_30]
0x180033d36  call    ??1?$OnDeleteIf@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@QEAA@XZ; OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>(void)
0x180033d3b  nop
0x180033d3c  lea     rcx, [rbp+var_40]
0x180033d40  call    ??1?$OnDeleteIf@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@QEAA@XZ; OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>(void)
0x180033d45  nop
0x180033d46  lea     rcx, [rbp+var_50]
0x180033d4a  call    ??1?$OnDeleteIf@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@@QEAA@XZ; OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>::~OnDeleteIf<void *,void (*)(void *),&CoTaskMemFree(void *)>(void)
0x180033d4f  mov     eax, ebx
0x180033d51  add     rsp, 78h
0x180033d55  pop     r15
0x180033d57  pop     r14
0x180033d59  pop     r13
0x180033d5b  pop     r12
0x180033d5d  pop     rdi
0x180033d5e  pop     rsi
0x180033d5f  pop     rbx
0x180033d60  pop     rbp
0x180033d61  retn
```

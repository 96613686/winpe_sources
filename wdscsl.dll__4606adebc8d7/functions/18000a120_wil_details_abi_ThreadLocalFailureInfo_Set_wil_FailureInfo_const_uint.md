# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000a120`
- end: `0x18000a384`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `612`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a4b4`

## callees

- `0x180008344`
- `0x18000a120`
- `0x18000d6d2`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000a27e`
- `msvcrt!memcpy_s` at `0x18000a2d9`
- `msvcrt!memcpy_s` at `0x18000a335`
- `msvcrt!memcpy_s` at `0x18000a27e`
- `msvcrt!memcpy_s` at `0x18000a2d9`
- `msvcrt!memcpy_s` at `0x18000a335`
- `KERNEL32!HeapFree` at `0x18000a226`
- `KERNEL32!HeapFree` at `0x18000a226`
- `KERNEL32!GetProcessHeap` at `0x18000a212`
- `KERNEL32!GetProcessHeap` at `0x18000a212`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v4; // r12
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rdx
  unsigned __int64 v15; // rbp
  rsize_t *v16; // rdi
  LPVOID v17; // r14
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char **v22; // rdi
  _BYTE *v23; // r8
  char *v24; // r14
  __int64 v25; // rbp
  rsize_t v26; // rbp
  _BYTE *v27; // r8
  char **v28; // rdi
  __int64 v29; // rbp
  rsize_t v30; // rbp
  _WORD *v31; // r8
  char **v32; // rdi
  unsigned __int64 v33; // rsi

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  v4 = -1;
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  if ( v6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_BYTE *)(v6 + v8) );
    v7 = v8 + 1;
  }
  else
  {
    v7 = 1;
  }
  v9 = *((_QWORD *)a2 + 16);
  if ( v9 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v9 + v11) );
    v10 = v11 + 1;
  }
  else
  {
    v10 = 1;
  }
  v12 = *((_QWORD *)a2 + 3);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * v14 + 2;
  }
  else
  {
    v13 = 2;
  }
  v15 = v7 + v13 + v10;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v7 + v13 + v10);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = *v16;
    v22 = (char **)((char *)this + 16);
    v23 = (_BYTE *)*((_QWORD *)a2 + 7);
    v24 = &v20[v21];
    if ( v20 == &v20[v21] )
      goto LABEL_30;
    if ( !v23 )
      goto LABEL_30;
    if ( !*v23 )
      goto LABEL_30;
    v25 = -1;
    do
      ++v25;
    while ( v23[v25] );
    v26 = v25 + 1;
    if ( v21 >= v26 )
    {
      memcpy_s(*((void *const *)this + 8), v21, v23, v26);
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
        *v22 = v20;
      v20 += v26;
    }
    else
    {
LABEL_30:
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
        *v22 = 0;
    }
    v27 = (_BYTE *)*((_QWORD *)a2 + 16);
    v28 = (char **)((char *)this + 32);
    if ( v20 == v24 )
      goto LABEL_41;
    if ( !v27 )
      goto LABEL_41;
    if ( !*v27 )
      goto LABEL_41;
    v29 = -1;
    do
      ++v29;
    while ( v27[v29] );
    v30 = v29 + 1;
    if ( v24 - v20 >= v30 )
    {
      memcpy_s(v20, v24 - v20, v27, v30);
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-32LL )
        *v28 = v20;
      v20 += v30;
    }
    else
    {
LABEL_41:
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-32LL )
        *v28 = 0;
    }
    v31 = (_WORD *)*((_QWORD *)a2 + 3);
    v32 = (char **)((char *)this + 56);
    if ( v20 == v24 || !v31 || !*v31 )
      goto LABEL_51;
    do
      ++v4;
    while ( v31[v4] );
    v33 = 2 * v4 + 2;
    if ( v24 - v20 >= v33 )
    {
      memcpy_s(v20, v24 - v20, v31, 2 * v4 + 2);
      if ( v32 )
        *v32 = v20;
      v20 += v33;
    }
    else
    {
LABEL_51:
      if ( v32 )
        *v32 = 0;
    }
    memset_0(v20, 0, v24 - v20);
  }
}

```

## disassembly

```asm
0x18000a120  mov     [rsp+arg_0], rbx
0x18000a125  mov     [rsp+arg_8], rbp
0x18000a12a  mov     [rsp+arg_10], rsi
0x18000a12f  push    rdi
0x18000a130  push    r12
0x18000a132  push    r13
0x18000a134  push    r14
0x18000a136  push    r15
0x18000a138  sub     rsp, 20h
0x18000a13c  mov     [rcx+4], r8d
0x18000a140  xor     r13d, r13d
0x18000a143  mov     eax, [rdx+8]
0x18000a146  mov     rsi, rcx
0x18000a149  mov     [rcx+8], eax
0x18000a14c  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000a150  mov     [rcx+10h], r13
0x18000a154  mov     r15, rdx
0x18000a157  movzx   eax, word ptr [rdx+40h]
0x18000a15b  mov     [rcx+18h], ax
0x18000a15f  mov     al, [rdx]
0x18000a161  mov     [rcx+1Ah], al
0x18000a164  mov     [rcx+20h], r13
0x18000a168  mov     rax, [rdx+88h]
0x18000a16f  mov     [rcx+28h], rax
0x18000a173  mov     rax, [rdx+90h]
0x18000a17a  mov     [rcx+30h], rax
0x18000a17e  mov     [rcx+38h], r13
0x18000a182  mov     rcx, [rdx+38h]
0x18000a186  test    rcx, rcx
0x18000a189  jnz     short loc_18000A190
0x18000a18b  lea     eax, [rcx+1]
0x18000a18e  jmp     short loc_18000A19F
0x18000a190  mov     rax, r12
0x18000a193  inc     rax
0x18000a196  cmp     [rcx+rax], r13b
0x18000a19a  jnz     short loc_18000A193
0x18000a19c  inc     rax
0x18000a19f  mov     rdx, [rdx+80h]
0x18000a1a6  test    rdx, rdx
0x18000a1a9  jnz     short loc_18000A1B0
0x18000a1ab  lea     ecx, [rdx+1]
0x18000a1ae  jmp     short loc_18000A1BF
0x18000a1b0  mov     rcx, r12
0x18000a1b3  inc     rcx
0x18000a1b6  cmp     [rdx+rcx], r13b
0x18000a1ba  jnz     short loc_18000A1B3
0x18000a1bc  inc     rcx
0x18000a1bf  mov     r8, [r15+18h]; unsigned __int64
0x18000a1c3  test    r8, r8
0x18000a1c6  jnz     short loc_18000A1CE
0x18000a1c8  lea     edx, [r8+2]
0x18000a1cc  jmp     short loc_18000A1E3
0x18000a1ce  mov     rdx, r12
0x18000a1d1  inc     rdx
0x18000a1d4  cmp     [r8+rdx*2], r13w
0x18000a1d9  jnz     short loc_18000A1D1
0x18000a1db  lea     rdx, ds:2[rdx*2]
0x18000a1e3  lea     rbp, [rdx+rcx]
0x18000a1e7  add     rbp, rax
0x18000a1ea  lea     rdi, [rsi+48h]
0x18000a1ee  cmp     [rsi+40h], r13
0x18000a1f2  jz      short loc_18000A1F9
0x18000a1f4  cmp     [rdi], rbp
0x18000a1f7  jnb     short loc_18000A239
0x18000a1f9  mov     rdx, rbp; dwBytes
0x18000a1fc  mov     ecx, 8; dwFlags
0x18000a201  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a206  mov     r14, rax
0x18000a209  test    rax, rax
0x18000a20c  jz      short loc_18000A239
0x18000a20e  mov     rbx, [rsi+40h]
0x18000a212  call    cs:__imp_GetProcessHeap
0x18000a219  nop     dword ptr [rax+rax+00h]
0x18000a21e  mov     r8, rbx; lpMem
0x18000a221  xor     edx, edx; dwFlags
0x18000a223  mov     rcx, rax; hHeap
0x18000a226  call    cs:__imp_HeapFree
0x18000a22d  nop     dword ptr [rax+rax+00h]
0x18000a232  mov     [rsi+40h], r14
0x18000a236  mov     [rdi], rbp
0x18000a239  mov     rbx, [rsi+40h]
0x18000a23d  test    rbx, rbx
0x18000a240  jz      loc_18000A366
0x18000a246  mov     rdx, [rdi]; DestinationSize
0x18000a249  lea     rdi, [rsi+10h]
0x18000a24d  mov     r8, [r15+38h]; Source
0x18000a251  lea     r14, [rdx+rbx]
0x18000a255  cmp     rbx, r14
0x18000a258  jz      short loc_18000A297
0x18000a25a  test    r8, r8
0x18000a25d  jz      short loc_18000A297
0x18000a25f  cmp     [r8], r13b
0x18000a262  jz      short loc_18000A297
0x18000a264  mov     rbp, r12
0x18000a267  inc     rbp
0x18000a26a  cmp     [r8+rbp], r13b
0x18000a26e  jnz     short loc_18000A267
0x18000a270  inc     rbp
0x18000a273  cmp     rdx, rbp
0x18000a276  jb      short loc_18000A297
0x18000a278  mov     r9, rbp; SourceSize
0x18000a27b  mov     rcx, rbx; Destination
0x18000a27e  call    cs:__imp_memcpy_s
0x18000a285  nop     dword ptr [rax+rax+00h]
0x18000a28a  test    rdi, rdi
0x18000a28d  jz      short loc_18000A292
0x18000a28f  mov     [rdi], rbx
0x18000a292  add     rbx, rbp
0x18000a295  jmp     short loc_18000A29F
0x18000a297  test    rdi, rdi
0x18000a29a  jz      short loc_18000A29F
0x18000a29c  mov     [rdi], r13
0x18000a29f  mov     r8, [r15+80h]; Source
0x18000a2a6  lea     rdi, [rsi+20h]
0x18000a2aa  cmp     rbx, r14
0x18000a2ad  jz      short loc_18000A2F2
0x18000a2af  test    r8, r8
0x18000a2b2  jz      short loc_18000A2F2
0x18000a2b4  cmp     [r8], r13b
0x18000a2b7  jz      short loc_18000A2F2
0x18000a2b9  mov     rbp, r12
0x18000a2bc  inc     rbp
0x18000a2bf  cmp     [r8+rbp], r13b
0x18000a2c3  jnz     short loc_18000A2BC
0x18000a2c5  mov     rdx, r14
0x18000a2c8  inc     rbp
0x18000a2cb  sub     rdx, rbx; DestinationSize
0x18000a2ce  cmp     rdx, rbp
0x18000a2d1  jb      short loc_18000A2F2
0x18000a2d3  mov     r9, rbp; SourceSize
0x18000a2d6  mov     rcx, rbx; Destination
0x18000a2d9  call    cs:__imp_memcpy_s
0x18000a2e0  nop     dword ptr [rax+rax+00h]
0x18000a2e5  test    rdi, rdi
0x18000a2e8  jz      short loc_18000A2ED
0x18000a2ea  mov     [rdi], rbx
0x18000a2ed  add     rbx, rbp
0x18000a2f0  jmp     short loc_18000A2FA
0x18000a2f2  test    rdi, rdi
0x18000a2f5  jz      short loc_18000A2FA
0x18000a2f7  mov     [rdi], r13
0x18000a2fa  mov     r8, [r15+18h]; Source
0x18000a2fe  lea     rdi, [rsi+38h]
0x18000a302  cmp     rbx, r14
0x18000a305  jz      short loc_18000A34E
0x18000a307  test    r8, r8
0x18000a30a  jz      short loc_18000A34E
0x18000a30c  cmp     [r8], r13w
0x18000a310  jz      short loc_18000A34E
0x18000a312  inc     r12
0x18000a315  cmp     [r8+r12*2], r13w
0x18000a31a  jnz     short loc_18000A312
0x18000a31c  mov     rdx, r14
0x18000a31f  lea     rsi, ds:2[r12*2]
0x18000a327  sub     rdx, rbx; DestinationSize
0x18000a32a  cmp     rdx, rsi
0x18000a32d  jb      short loc_18000A34E
0x18000a32f  mov     r9, rsi; SourceSize
0x18000a332  mov     rcx, rbx; Destination
0x18000a335  call    cs:__imp_memcpy_s
0x18000a33c  nop     dword ptr [rax+rax+00h]
0x18000a341  test    rdi, rdi
0x18000a344  jz      short loc_18000A349
0x18000a346  mov     [rdi], rbx
0x18000a349  add     rbx, rsi
0x18000a34c  jmp     short loc_18000A356
0x18000a34e  test    rdi, rdi
0x18000a351  jz      short loc_18000A356
0x18000a353  mov     [rdi], r13
0x18000a356  sub     r14, rbx
0x18000a359  xor     edx, edx; Val
0x18000a35b  mov     r8, r14; Size
0x18000a35e  mov     rcx, rbx; void *
0x18000a361  call    memset_0
0x18000a366  mov     rbx, [rsp+48h+arg_0]
0x18000a36b  mov     rbp, [rsp+48h+arg_8]
0x18000a370  mov     rsi, [rsp+48h+arg_10]
0x18000a375  add     rsp, 20h
0x18000a379  pop     r15
0x18000a37b  pop     r14
0x18000a37d  pop     r13
0x18000a37f  pop     r12
0x18000a381  pop     rdi
0x18000a382  retn
```

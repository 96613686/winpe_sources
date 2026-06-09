# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000d3f0`
- end: `0x18000d654`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `612`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d784`

## callees

- `0x18000bf30`
- `0x18000d3f0`
- `0x180030362`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000d54e`
- `msvcrt!memcpy_s` at `0x18000d5a9`
- `msvcrt!memcpy_s` at `0x18000d605`
- `msvcrt!memcpy_s` at `0x18000d54e`
- `msvcrt!memcpy_s` at `0x18000d5a9`
- `msvcrt!memcpy_s` at `0x18000d605`
- `KERNEL32!GetProcessHeap` at `0x18000d4e2`
- `KERNEL32!GetProcessHeap` at `0x18000d4e2`
- `KERNEL32!HeapFree` at `0x18000d4f6`
- `KERNEL32!HeapFree` at `0x18000d4f6`

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
0x18000d3f0  mov     [rsp+arg_0], rbx
0x18000d3f5  mov     [rsp+arg_8], rbp
0x18000d3fa  mov     [rsp+arg_10], rsi
0x18000d3ff  push    rdi
0x18000d400  push    r12
0x18000d402  push    r13
0x18000d404  push    r14
0x18000d406  push    r15
0x18000d408  sub     rsp, 20h
0x18000d40c  mov     [rcx+4], r8d
0x18000d410  xor     r13d, r13d
0x18000d413  mov     eax, [rdx+8]
0x18000d416  mov     rsi, rcx
0x18000d419  mov     [rcx+8], eax
0x18000d41c  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000d420  mov     [rcx+10h], r13
0x18000d424  mov     r15, rdx
0x18000d427  movzx   eax, word ptr [rdx+40h]
0x18000d42b  mov     [rcx+18h], ax
0x18000d42f  mov     al, [rdx]
0x18000d431  mov     [rcx+1Ah], al
0x18000d434  mov     [rcx+20h], r13
0x18000d438  mov     rax, [rdx+88h]
0x18000d43f  mov     [rcx+28h], rax
0x18000d443  mov     rax, [rdx+90h]
0x18000d44a  mov     [rcx+30h], rax
0x18000d44e  mov     [rcx+38h], r13
0x18000d452  mov     rcx, [rdx+38h]
0x18000d456  test    rcx, rcx
0x18000d459  jnz     short loc_18000D460
0x18000d45b  lea     eax, [rcx+1]
0x18000d45e  jmp     short loc_18000D46F
0x18000d460  mov     rax, r12
0x18000d463  inc     rax
0x18000d466  cmp     [rcx+rax], r13b
0x18000d46a  jnz     short loc_18000D463
0x18000d46c  inc     rax
0x18000d46f  mov     rdx, [rdx+80h]
0x18000d476  test    rdx, rdx
0x18000d479  jnz     short loc_18000D480
0x18000d47b  lea     ecx, [rdx+1]
0x18000d47e  jmp     short loc_18000D48F
0x18000d480  mov     rcx, r12
0x18000d483  inc     rcx
0x18000d486  cmp     [rdx+rcx], r13b
0x18000d48a  jnz     short loc_18000D483
0x18000d48c  inc     rcx
0x18000d48f  mov     r8, [r15+18h]; unsigned __int64
0x18000d493  test    r8, r8
0x18000d496  jnz     short loc_18000D49E
0x18000d498  lea     edx, [r8+2]
0x18000d49c  jmp     short loc_18000D4B3
0x18000d49e  mov     rdx, r12
0x18000d4a1  inc     rdx
0x18000d4a4  cmp     [r8+rdx*2], r13w
0x18000d4a9  jnz     short loc_18000D4A1
0x18000d4ab  lea     rdx, ds:2[rdx*2]
0x18000d4b3  lea     rbp, [rdx+rcx]
0x18000d4b7  add     rbp, rax
0x18000d4ba  lea     rdi, [rsi+48h]
0x18000d4be  cmp     [rsi+40h], r13
0x18000d4c2  jz      short loc_18000D4C9
0x18000d4c4  cmp     [rdi], rbp
0x18000d4c7  jnb     short loc_18000D509
0x18000d4c9  mov     rdx, rbp; dwBytes
0x18000d4cc  mov     ecx, 8; dwFlags
0x18000d4d1  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000d4d6  mov     r14, rax
0x18000d4d9  test    rax, rax
0x18000d4dc  jz      short loc_18000D509
0x18000d4de  mov     rbx, [rsi+40h]
0x18000d4e2  call    cs:__imp_GetProcessHeap
0x18000d4e9  nop     dword ptr [rax+rax+00h]
0x18000d4ee  mov     r8, rbx; lpMem
0x18000d4f1  xor     edx, edx; dwFlags
0x18000d4f3  mov     rcx, rax; hHeap
0x18000d4f6  call    cs:__imp_HeapFree
0x18000d4fd  nop     dword ptr [rax+rax+00h]
0x18000d502  mov     [rsi+40h], r14
0x18000d506  mov     [rdi], rbp
0x18000d509  mov     rbx, [rsi+40h]
0x18000d50d  test    rbx, rbx
0x18000d510  jz      loc_18000D636
0x18000d516  mov     rdx, [rdi]; DestinationSize
0x18000d519  lea     rdi, [rsi+10h]
0x18000d51d  mov     r8, [r15+38h]; Source
0x18000d521  lea     r14, [rdx+rbx]
0x18000d525  cmp     rbx, r14
0x18000d528  jz      short loc_18000D567
0x18000d52a  test    r8, r8
0x18000d52d  jz      short loc_18000D567
0x18000d52f  cmp     [r8], r13b
0x18000d532  jz      short loc_18000D567
0x18000d534  mov     rbp, r12
0x18000d537  inc     rbp
0x18000d53a  cmp     [r8+rbp], r13b
0x18000d53e  jnz     short loc_18000D537
0x18000d540  inc     rbp
0x18000d543  cmp     rdx, rbp
0x18000d546  jb      short loc_18000D567
0x18000d548  mov     r9, rbp; SourceSize
0x18000d54b  mov     rcx, rbx; Destination
0x18000d54e  call    cs:__imp_memcpy_s
0x18000d555  nop     dword ptr [rax+rax+00h]
0x18000d55a  test    rdi, rdi
0x18000d55d  jz      short loc_18000D562
0x18000d55f  mov     [rdi], rbx
0x18000d562  add     rbx, rbp
0x18000d565  jmp     short loc_18000D56F
0x18000d567  test    rdi, rdi
0x18000d56a  jz      short loc_18000D56F
0x18000d56c  mov     [rdi], r13
0x18000d56f  mov     r8, [r15+80h]; Source
0x18000d576  lea     rdi, [rsi+20h]
0x18000d57a  cmp     rbx, r14
0x18000d57d  jz      short loc_18000D5C2
0x18000d57f  test    r8, r8
0x18000d582  jz      short loc_18000D5C2
0x18000d584  cmp     [r8], r13b
0x18000d587  jz      short loc_18000D5C2
0x18000d589  mov     rbp, r12
0x18000d58c  inc     rbp
0x18000d58f  cmp     [r8+rbp], r13b
0x18000d593  jnz     short loc_18000D58C
0x18000d595  mov     rdx, r14
0x18000d598  inc     rbp
0x18000d59b  sub     rdx, rbx; DestinationSize
0x18000d59e  cmp     rdx, rbp
0x18000d5a1  jb      short loc_18000D5C2
0x18000d5a3  mov     r9, rbp; SourceSize
0x18000d5a6  mov     rcx, rbx; Destination
0x18000d5a9  call    cs:__imp_memcpy_s
0x18000d5b0  nop     dword ptr [rax+rax+00h]
0x18000d5b5  test    rdi, rdi
0x18000d5b8  jz      short loc_18000D5BD
0x18000d5ba  mov     [rdi], rbx
0x18000d5bd  add     rbx, rbp
0x18000d5c0  jmp     short loc_18000D5CA
0x18000d5c2  test    rdi, rdi
0x18000d5c5  jz      short loc_18000D5CA
0x18000d5c7  mov     [rdi], r13
0x18000d5ca  mov     r8, [r15+18h]; Source
0x18000d5ce  lea     rdi, [rsi+38h]
0x18000d5d2  cmp     rbx, r14
0x18000d5d5  jz      short loc_18000D61E
0x18000d5d7  test    r8, r8
0x18000d5da  jz      short loc_18000D61E
0x18000d5dc  cmp     [r8], r13w
0x18000d5e0  jz      short loc_18000D61E
0x18000d5e2  inc     r12
0x18000d5e5  cmp     [r8+r12*2], r13w
0x18000d5ea  jnz     short loc_18000D5E2
0x18000d5ec  mov     rdx, r14
0x18000d5ef  lea     rsi, ds:2[r12*2]
0x18000d5f7  sub     rdx, rbx; DestinationSize
0x18000d5fa  cmp     rdx, rsi
0x18000d5fd  jb      short loc_18000D61E
0x18000d5ff  mov     r9, rsi; SourceSize
0x18000d602  mov     rcx, rbx; Destination
0x18000d605  call    cs:__imp_memcpy_s
0x18000d60c  nop     dword ptr [rax+rax+00h]
0x18000d611  test    rdi, rdi
0x18000d614  jz      short loc_18000D619
0x18000d616  mov     [rdi], rbx
0x18000d619  add     rbx, rsi
0x18000d61c  jmp     short loc_18000D626
0x18000d61e  test    rdi, rdi
0x18000d621  jz      short loc_18000D626
0x18000d623  mov     [rdi], r13
0x18000d626  sub     r14, rbx
0x18000d629  xor     edx, edx; Val
0x18000d62b  mov     r8, r14; Size
0x18000d62e  mov     rcx, rbx; void *
0x18000d631  call    memset_0
0x18000d636  mov     rbx, [rsp+48h+arg_0]
0x18000d63b  mov     rbp, [rsp+48h+arg_8]
0x18000d640  mov     rsi, [rsp+48h+arg_10]
0x18000d645  add     rsp, 20h
0x18000d649  pop     r15
0x18000d64b  pop     r14
0x18000d64d  pop     r13
0x18000d64f  pop     r12
0x18000d651  pop     rdi
0x18000d652  retn
```

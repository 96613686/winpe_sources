# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000f64c`
- end: `0x18000f8b0`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `612`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fa7c`

## callees

- `0x18000ce30`
- `0x18000f64c`
- `0x180011a62`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000f7aa`
- `msvcrt!memcpy_s` at `0x18000f805`
- `msvcrt!memcpy_s` at `0x18000f861`
- `msvcrt!memcpy_s` at `0x18000f7aa`
- `msvcrt!memcpy_s` at `0x18000f805`
- `msvcrt!memcpy_s` at `0x18000f861`
- `KERNEL32!GetProcessHeap` at `0x18000f73e`
- `KERNEL32!GetProcessHeap` at `0x18000f73e`
- `KERNEL32!HeapFree` at `0x18000f752`
- `KERNEL32!HeapFree` at `0x18000f752`

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
0x18000f64c  mov     [rsp+arg_0], rbx
0x18000f651  mov     [rsp+arg_8], rbp
0x18000f656  mov     [rsp+arg_10], rsi
0x18000f65b  push    rdi
0x18000f65c  push    r12
0x18000f65e  push    r13
0x18000f660  push    r14
0x18000f662  push    r15
0x18000f664  sub     rsp, 20h
0x18000f668  mov     [rcx+4], r8d
0x18000f66c  xor     r13d, r13d
0x18000f66f  mov     eax, [rdx+8]
0x18000f672  mov     rsi, rcx
0x18000f675  mov     [rcx+8], eax
0x18000f678  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000f67c  mov     [rcx+10h], r13
0x18000f680  mov     r15, rdx
0x18000f683  movzx   eax, word ptr [rdx+40h]
0x18000f687  mov     [rcx+18h], ax
0x18000f68b  mov     al, [rdx]
0x18000f68d  mov     [rcx+1Ah], al
0x18000f690  mov     [rcx+20h], r13
0x18000f694  mov     rax, [rdx+88h]
0x18000f69b  mov     [rcx+28h], rax
0x18000f69f  mov     rax, [rdx+90h]
0x18000f6a6  mov     [rcx+30h], rax
0x18000f6aa  mov     [rcx+38h], r13
0x18000f6ae  mov     rcx, [rdx+38h]
0x18000f6b2  test    rcx, rcx
0x18000f6b5  jnz     short loc_18000F6BC
0x18000f6b7  lea     eax, [rcx+1]
0x18000f6ba  jmp     short loc_18000F6CB
0x18000f6bc  mov     rax, r12
0x18000f6bf  inc     rax
0x18000f6c2  cmp     [rcx+rax], r13b
0x18000f6c6  jnz     short loc_18000F6BF
0x18000f6c8  inc     rax
0x18000f6cb  mov     rdx, [rdx+80h]
0x18000f6d2  test    rdx, rdx
0x18000f6d5  jnz     short loc_18000F6DC
0x18000f6d7  lea     ecx, [rdx+1]
0x18000f6da  jmp     short loc_18000F6EB
0x18000f6dc  mov     rcx, r12
0x18000f6df  inc     rcx
0x18000f6e2  cmp     [rdx+rcx], r13b
0x18000f6e6  jnz     short loc_18000F6DF
0x18000f6e8  inc     rcx
0x18000f6eb  mov     r8, [r15+18h]; unsigned __int64
0x18000f6ef  test    r8, r8
0x18000f6f2  jnz     short loc_18000F6FA
0x18000f6f4  lea     edx, [r8+2]
0x18000f6f8  jmp     short loc_18000F70F
0x18000f6fa  mov     rdx, r12
0x18000f6fd  inc     rdx
0x18000f700  cmp     [r8+rdx*2], r13w
0x18000f705  jnz     short loc_18000F6FD
0x18000f707  lea     rdx, ds:2[rdx*2]
0x18000f70f  lea     rbp, [rdx+rcx]
0x18000f713  add     rbp, rax
0x18000f716  lea     rdi, [rsi+48h]
0x18000f71a  cmp     [rsi+40h], r13
0x18000f71e  jz      short loc_18000F725
0x18000f720  cmp     [rdi], rbp
0x18000f723  jnb     short loc_18000F765
0x18000f725  mov     rdx, rbp; dwBytes
0x18000f728  mov     ecx, 8; dwFlags
0x18000f72d  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000f732  mov     r14, rax
0x18000f735  test    rax, rax
0x18000f738  jz      short loc_18000F765
0x18000f73a  mov     rbx, [rsi+40h]
0x18000f73e  call    cs:__imp_GetProcessHeap
0x18000f745  nop     dword ptr [rax+rax+00h]
0x18000f74a  mov     r8, rbx; lpMem
0x18000f74d  xor     edx, edx; dwFlags
0x18000f74f  mov     rcx, rax; hHeap
0x18000f752  call    cs:__imp_HeapFree
0x18000f759  nop     dword ptr [rax+rax+00h]
0x18000f75e  mov     [rsi+40h], r14
0x18000f762  mov     [rdi], rbp
0x18000f765  mov     rbx, [rsi+40h]
0x18000f769  test    rbx, rbx
0x18000f76c  jz      loc_18000F892
0x18000f772  mov     rdx, [rdi]; DestinationSize
0x18000f775  lea     rdi, [rsi+10h]
0x18000f779  mov     r8, [r15+38h]; Source
0x18000f77d  lea     r14, [rdx+rbx]
0x18000f781  cmp     rbx, r14
0x18000f784  jz      short loc_18000F7C3
0x18000f786  test    r8, r8
0x18000f789  jz      short loc_18000F7C3
0x18000f78b  cmp     [r8], r13b
0x18000f78e  jz      short loc_18000F7C3
0x18000f790  mov     rbp, r12
0x18000f793  inc     rbp
0x18000f796  cmp     [r8+rbp], r13b
0x18000f79a  jnz     short loc_18000F793
0x18000f79c  inc     rbp
0x18000f79f  cmp     rdx, rbp
0x18000f7a2  jb      short loc_18000F7C3
0x18000f7a4  mov     r9, rbp; SourceSize
0x18000f7a7  mov     rcx, rbx; Destination
0x18000f7aa  call    cs:__imp_memcpy_s
0x18000f7b1  nop     dword ptr [rax+rax+00h]
0x18000f7b6  test    rdi, rdi
0x18000f7b9  jz      short loc_18000F7BE
0x18000f7bb  mov     [rdi], rbx
0x18000f7be  add     rbx, rbp
0x18000f7c1  jmp     short loc_18000F7CB
0x18000f7c3  test    rdi, rdi
0x18000f7c6  jz      short loc_18000F7CB
0x18000f7c8  mov     [rdi], r13
0x18000f7cb  mov     r8, [r15+80h]; Source
0x18000f7d2  lea     rdi, [rsi+20h]
0x18000f7d6  cmp     rbx, r14
0x18000f7d9  jz      short loc_18000F81E
0x18000f7db  test    r8, r8
0x18000f7de  jz      short loc_18000F81E
0x18000f7e0  cmp     [r8], r13b
0x18000f7e3  jz      short loc_18000F81E
0x18000f7e5  mov     rbp, r12
0x18000f7e8  inc     rbp
0x18000f7eb  cmp     [r8+rbp], r13b
0x18000f7ef  jnz     short loc_18000F7E8
0x18000f7f1  mov     rdx, r14
0x18000f7f4  inc     rbp
0x18000f7f7  sub     rdx, rbx; DestinationSize
0x18000f7fa  cmp     rdx, rbp
0x18000f7fd  jb      short loc_18000F81E
0x18000f7ff  mov     r9, rbp; SourceSize
0x18000f802  mov     rcx, rbx; Destination
0x18000f805  call    cs:__imp_memcpy_s
0x18000f80c  nop     dword ptr [rax+rax+00h]
0x18000f811  test    rdi, rdi
0x18000f814  jz      short loc_18000F819
0x18000f816  mov     [rdi], rbx
0x18000f819  add     rbx, rbp
0x18000f81c  jmp     short loc_18000F826
0x18000f81e  test    rdi, rdi
0x18000f821  jz      short loc_18000F826
0x18000f823  mov     [rdi], r13
0x18000f826  mov     r8, [r15+18h]; Source
0x18000f82a  lea     rdi, [rsi+38h]
0x18000f82e  cmp     rbx, r14
0x18000f831  jz      short loc_18000F87A
0x18000f833  test    r8, r8
0x18000f836  jz      short loc_18000F87A
0x18000f838  cmp     [r8], r13w
0x18000f83c  jz      short loc_18000F87A
0x18000f83e  inc     r12
0x18000f841  cmp     [r8+r12*2], r13w
0x18000f846  jnz     short loc_18000F83E
0x18000f848  mov     rdx, r14
0x18000f84b  lea     rsi, ds:2[r12*2]
0x18000f853  sub     rdx, rbx; DestinationSize
0x18000f856  cmp     rdx, rsi
0x18000f859  jb      short loc_18000F87A
0x18000f85b  mov     r9, rsi; SourceSize
0x18000f85e  mov     rcx, rbx; Destination
0x18000f861  call    cs:__imp_memcpy_s
0x18000f868  nop     dword ptr [rax+rax+00h]
0x18000f86d  test    rdi, rdi
0x18000f870  jz      short loc_18000F875
0x18000f872  mov     [rdi], rbx
0x18000f875  add     rbx, rsi
0x18000f878  jmp     short loc_18000F882
0x18000f87a  test    rdi, rdi
0x18000f87d  jz      short loc_18000F882
0x18000f87f  mov     [rdi], r13
0x18000f882  sub     r14, rbx
0x18000f885  xor     edx, edx; Val
0x18000f887  mov     r8, r14; Size
0x18000f88a  mov     rcx, rbx; void *
0x18000f88d  call    memset_0
0x18000f892  mov     rbx, [rsp+48h+arg_0]
0x18000f897  mov     rbp, [rsp+48h+arg_8]
0x18000f89c  mov     rsi, [rsp+48h+arg_10]
0x18000f8a1  add     rsp, 20h
0x18000f8a5  pop     r15
0x18000f8a7  pop     r14
0x18000f8a9  pop     r13
0x18000f8ab  pop     r12
0x18000f8ad  pop     rdi
0x18000f8ae  retn
```

# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180003bb0`
- end: `0x180003db0`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `512`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004010`

## callees

- `0x180001ab4`
- `0x18000215c`
- `0x180003bb0`
- `0x1800044a4`
- `0x180015a80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cb1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ca3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ca3`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v4; // r15
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // rbp
  rsize_t *v16; // rdi
  LPVOID v17; // r14
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char **v22; // rdi
  _BYTE *v23; // r8
  char *v24; // rbp
  __int64 v25; // rax
  __int64 v26; // r14
  _BYTE *v27; // r8
  char **v28; // rdi
  void *v29; // rax

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
  v7 = 1;
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(v6 + v9) );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 1;
  }
  v10 = *((_QWORD *)a2 + 16);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v10 + v11) );
    v7 = v11 + 1;
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
  v15 = v8 + v13 + v7;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v8 + v13 + v7);
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
      goto LABEL_29;
    if ( !v23 )
      goto LABEL_29;
    if ( !*v23 )
      goto LABEL_29;
    v25 = -1;
    do
      ++v25;
    while ( v23[v25] );
    v26 = v25 + 1;
    if ( v21 >= v25 + 1 )
    {
      memcpy_s(*((void *const *)this + 8), v21, v23, v25 + 1);
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
        *v22 = v20;
      v20 += v26;
    }
    else
    {
LABEL_29:
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
        *v22 = 0;
    }
    v27 = (_BYTE *)*((_QWORD *)a2 + 16);
    v28 = (char **)((char *)this + 32);
    if ( v20 == v24 || !v27 || !*v27 )
      goto LABEL_39;
    do
      ++v4;
    while ( v27[v4] );
    if ( v24 - v20 >= (unsigned __int64)(v4 + 1) )
    {
      memcpy_s(v20, v24 - v20, v27, v4 + 1);
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-32LL )
        *v28 = v20;
      v20 += v4 + 1;
    }
    else
    {
LABEL_39:
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-32LL )
        *v28 = 0;
    }
    v29 = (void *)wil::details::WriteResultString<wchar_t const *>(v20, v24, *((_QWORD *)a2 + 3), (char *)this + 56);
    memset(v29, 0, v24 - (_BYTE *)v29);
  }
}

```

## disassembly

```asm
0x180003bb0  mov     [rsp+arg_0], rbx
0x180003bb5  mov     [rsp+arg_8], rbp
0x180003bba  mov     [rsp+arg_10], rsi
0x180003bbf  push    rdi
0x180003bc0  push    r12
0x180003bc2  push    r13
0x180003bc4  push    r14
0x180003bc6  push    r15
0x180003bc8  sub     rsp, 20h
0x180003bcc  mov     [rcx+4], r8d
0x180003bd0  xor     r12d, r12d
0x180003bd3  mov     eax, [rdx+8]
0x180003bd6  mov     rsi, rcx
0x180003bd9  mov     [rcx+8], eax
0x180003bdc  or      r15, 0FFFFFFFFFFFFFFFFh
0x180003be0  mov     [rcx+10h], r12
0x180003be4  mov     r13, rdx
0x180003be7  movzx   eax, word ptr [rdx+40h]
0x180003beb  mov     [rcx+18h], ax
0x180003bef  mov     al, [rdx]
0x180003bf1  mov     [rcx+1Ah], al
0x180003bf4  mov     [rcx+20h], r12
0x180003bf8  mov     rax, [rdx+88h]
0x180003bff  mov     [rcx+28h], rax
0x180003c03  mov     rax, [rdx+90h]
0x180003c0a  mov     [rcx+30h], rax
0x180003c0e  mov     [rcx+38h], r12
0x180003c12  mov     rcx, [rdx+38h]
0x180003c16  lea     edx, [r12+1]
0x180003c1b  test    rcx, rcx
0x180003c1e  jnz     short loc_180003C25
0x180003c20  mov     r8d, edx
0x180003c23  jmp     short loc_180003C35
0x180003c25  mov     rax, r15
0x180003c28  inc     rax
0x180003c2b  cmp     [rcx+rax], r12b
0x180003c2f  jnz     short loc_180003C28
0x180003c31  lea     r8, [rax+1]; unsigned __int64
0x180003c35  mov     rcx, [r13+80h]
0x180003c3c  test    rcx, rcx
0x180003c3f  jz      short loc_180003C51
0x180003c41  mov     rax, r15
0x180003c44  inc     rax
0x180003c47  cmp     [rcx+rax], r12b
0x180003c4b  jnz     short loc_180003C44
0x180003c4d  lea     rdx, [rax+1]
0x180003c51  mov     rcx, [r13+18h]
0x180003c55  test    rcx, rcx
0x180003c58  jnz     short loc_180003C5F
0x180003c5a  lea     eax, [rcx+2]
0x180003c5d  jmp     short loc_180003C74
0x180003c5f  mov     rax, r15
0x180003c62  inc     rax
0x180003c65  cmp     [rcx+rax*2], r12w
0x180003c6a  jnz     short loc_180003C62
0x180003c6c  lea     rax, ds:2[rax*2]
0x180003c74  lea     rbp, [rax+rdx]
0x180003c78  add     rbp, r8
0x180003c7b  lea     rdi, [rsi+48h]
0x180003c7f  cmp     [rsi+40h], r12
0x180003c83  jz      short loc_180003C8A
0x180003c85  cmp     [rdi], rbp
0x180003c88  jnb     short loc_180003CBE
0x180003c8a  mov     rdx, rbp; dwBytes
0x180003c8d  mov     ecx, 8; dwFlags
0x180003c92  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003c97  mov     r14, rax
0x180003c9a  test    rax, rax
0x180003c9d  jz      short loc_180003CBE
0x180003c9f  mov     rbx, [rsi+40h]
0x180003ca3  call    cs:__imp_GetProcessHeap
0x180003ca9  mov     r8, rbx; lpMem
0x180003cac  xor     edx, edx; dwFlags
0x180003cae  mov     rcx, rax; hHeap
0x180003cb1  call    cs:__imp_HeapFree
0x180003cb7  mov     [rsi+40h], r14
0x180003cbb  mov     [rdi], rbp
0x180003cbe  mov     rbx, [rsi+40h]
0x180003cc2  test    rbx, rbx
0x180003cc5  jz      loc_180003D93
0x180003ccb  mov     rdx, [rdi]; DestinationSize
0x180003cce  lea     rdi, [rsi+10h]
0x180003cd2  mov     r8, [r13+38h]; Source
0x180003cd6  lea     rbp, [rdx+rbx]
0x180003cda  cmp     rbx, rbp
0x180003cdd  jz      short loc_180003D16
0x180003cdf  test    r8, r8
0x180003ce2  jz      short loc_180003D16
0x180003ce4  cmp     [r8], r12b
0x180003ce7  jz      short loc_180003D16
0x180003ce9  mov     rax, r15
0x180003cec  inc     rax
0x180003cef  cmp     [r8+rax], r12b
0x180003cf3  jnz     short loc_180003CEC
0x180003cf5  lea     r14, [rax+1]
0x180003cf9  cmp     rdx, r14
0x180003cfc  jb      short loc_180003D16
0x180003cfe  mov     r9, r14; SourceSize
0x180003d01  mov     rcx, rbx; Destination
0x180003d04  call    memcpy_s
0x180003d09  test    rdi, rdi
0x180003d0c  jz      short loc_180003D11
0x180003d0e  mov     [rdi], rbx
0x180003d11  add     rbx, r14
0x180003d14  jmp     short loc_180003D1E
0x180003d16  test    rdi, rdi
0x180003d19  jz      short loc_180003D1E
0x180003d1b  mov     [rdi], r12
0x180003d1e  mov     r8, [r13+80h]; Source
0x180003d25  lea     rdi, [rsi+20h]
0x180003d29  cmp     rbx, rbp
0x180003d2c  jz      short loc_180003D68
0x180003d2e  test    r8, r8
0x180003d31  jz      short loc_180003D68
0x180003d33  cmp     [r8], r12b
0x180003d36  jz      short loc_180003D68
0x180003d38  inc     r15
0x180003d3b  cmp     [r8+r15], r12b
0x180003d3f  jnz     short loc_180003D38
0x180003d41  mov     rdx, rbp
0x180003d44  lea     r14, [r15+1]
0x180003d48  sub     rdx, rbx; DestinationSize
0x180003d4b  cmp     rdx, r14
0x180003d4e  jb      short loc_180003D68
0x180003d50  mov     r9, r14; SourceSize
0x180003d53  mov     rcx, rbx; Destination
0x180003d56  call    memcpy_s
0x180003d5b  test    rdi, rdi
0x180003d5e  jz      short loc_180003D63
0x180003d60  mov     [rdi], rbx
0x180003d63  add     rbx, r14
0x180003d66  jmp     short loc_180003D70
0x180003d68  test    rdi, rdi
0x180003d6b  jz      short loc_180003D70
0x180003d6d  mov     [rdi], r12
0x180003d70  mov     r8, [r13+18h]
0x180003d74  lea     r9, [rsi+38h]
0x180003d78  mov     rdx, rbp
0x180003d7b  mov     rcx, rbx
0x180003d7e  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x180003d83  sub     rbp, rax
0x180003d86  xor     edx, edx; Val
0x180003d88  mov     r8, rbp; Size
0x180003d8b  mov     rcx, rax; void *
0x180003d8e  call    memset
0x180003d93  mov     rbx, [rsp+48h+arg_0]
0x180003d98  mov     rbp, [rsp+48h+arg_8]
0x180003d9d  mov     rsi, [rsp+48h+arg_10]
0x180003da2  add     rsp, 20h
0x180003da6  pop     r15
0x180003da8  pop     r14
0x180003daa  pop     r13
0x180003dac  pop     r12
0x180003dae  pop     rdi
0x180003daf  retn
```

# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800062c8`
- end: `0x1800064c8`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `512`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006730`

## callees

- `0x180003584`
- `0x180004348`
- `0x1800062c8`
- `0x180006c18`
- `0x180014960`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800063bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800063c9`

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
  char *v29; // rax

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
    v29 = wil::details::WriteResultString<wchar_t const *>(v20, v24, *((_WORD **)a2 + 3), (_QWORD *)this + 7);
    memset(v29, 0, v24 - v29);
  }
}

```

## disassembly

```asm
0x1800062c8  mov     [rsp+arg_0], rbx
0x1800062cd  mov     [rsp+arg_8], rbp
0x1800062d2  mov     [rsp+arg_10], rsi
0x1800062d7  push    rdi
0x1800062d8  push    r12
0x1800062da  push    r13
0x1800062dc  push    r14
0x1800062de  push    r15
0x1800062e0  sub     rsp, 20h
0x1800062e4  mov     [rcx+4], r8d
0x1800062e8  xor     r12d, r12d
0x1800062eb  mov     eax, [rdx+8]
0x1800062ee  mov     rsi, rcx
0x1800062f1  mov     [rcx+8], eax
0x1800062f4  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800062f8  mov     [rcx+10h], r12
0x1800062fc  mov     r13, rdx
0x1800062ff  movzx   eax, word ptr [rdx+40h]
0x180006303  mov     [rcx+18h], ax
0x180006307  mov     al, [rdx]
0x180006309  mov     [rcx+1Ah], al
0x18000630c  mov     [rcx+20h], r12
0x180006310  mov     rax, [rdx+88h]
0x180006317  mov     [rcx+28h], rax
0x18000631b  mov     rax, [rdx+90h]
0x180006322  mov     [rcx+30h], rax
0x180006326  mov     [rcx+38h], r12
0x18000632a  mov     rcx, [rdx+38h]
0x18000632e  lea     edx, [r12+1]
0x180006333  test    rcx, rcx
0x180006336  jnz     short loc_18000633D
0x180006338  mov     r8d, edx
0x18000633b  jmp     short loc_18000634D
0x18000633d  mov     rax, r15
0x180006340  inc     rax
0x180006343  cmp     [rcx+rax], r12b
0x180006347  jnz     short loc_180006340
0x180006349  lea     r8, [rax+1]; unsigned __int64
0x18000634d  mov     rcx, [r13+80h]
0x180006354  test    rcx, rcx
0x180006357  jz      short loc_180006369
0x180006359  mov     rax, r15
0x18000635c  inc     rax
0x18000635f  cmp     [rcx+rax], r12b
0x180006363  jnz     short loc_18000635C
0x180006365  lea     rdx, [rax+1]
0x180006369  mov     rcx, [r13+18h]
0x18000636d  test    rcx, rcx
0x180006370  jnz     short loc_180006377
0x180006372  lea     eax, [rcx+2]
0x180006375  jmp     short loc_18000638C
0x180006377  mov     rax, r15
0x18000637a  inc     rax
0x18000637d  cmp     [rcx+rax*2], r12w
0x180006382  jnz     short loc_18000637A
0x180006384  lea     rax, ds:2[rax*2]
0x18000638c  lea     rbp, [rax+rdx]
0x180006390  add     rbp, r8
0x180006393  lea     rdi, [rsi+48h]
0x180006397  cmp     [rsi+40h], r12
0x18000639b  jz      short loc_1800063A2
0x18000639d  cmp     [rdi], rbp
0x1800063a0  jnb     short loc_1800063D6
0x1800063a2  mov     rdx, rbp; dwBytes
0x1800063a5  mov     ecx, 8; dwFlags
0x1800063aa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800063af  mov     r14, rax
0x1800063b2  test    rax, rax
0x1800063b5  jz      short loc_1800063D6
0x1800063b7  mov     rbx, [rsi+40h]
0x1800063bb  call    cs:__imp_GetProcessHeap
0x1800063c1  mov     r8, rbx; lpMem
0x1800063c4  xor     edx, edx; dwFlags
0x1800063c6  mov     rcx, rax; hHeap
0x1800063c9  call    cs:__imp_HeapFree
0x1800063cf  mov     [rsi+40h], r14
0x1800063d3  mov     [rdi], rbp
0x1800063d6  mov     rbx, [rsi+40h]
0x1800063da  test    rbx, rbx
0x1800063dd  jz      loc_1800064AB
0x1800063e3  mov     rdx, [rdi]; DestinationSize
0x1800063e6  lea     rdi, [rsi+10h]
0x1800063ea  mov     r8, [r13+38h]; Source
0x1800063ee  lea     rbp, [rdx+rbx]
0x1800063f2  cmp     rbx, rbp
0x1800063f5  jz      short loc_18000642E
0x1800063f7  test    r8, r8
0x1800063fa  jz      short loc_18000642E
0x1800063fc  cmp     [r8], r12b
0x1800063ff  jz      short loc_18000642E
0x180006401  mov     rax, r15
0x180006404  inc     rax
0x180006407  cmp     [r8+rax], r12b
0x18000640b  jnz     short loc_180006404
0x18000640d  lea     r14, [rax+1]
0x180006411  cmp     rdx, r14
0x180006414  jb      short loc_18000642E
0x180006416  mov     r9, r14; SourceSize
0x180006419  mov     rcx, rbx; Destination
0x18000641c  call    memcpy_s
0x180006421  test    rdi, rdi
0x180006424  jz      short loc_180006429
0x180006426  mov     [rdi], rbx
0x180006429  add     rbx, r14
0x18000642c  jmp     short loc_180006436
0x18000642e  test    rdi, rdi
0x180006431  jz      short loc_180006436
0x180006433  mov     [rdi], r12
0x180006436  mov     r8, [r13+80h]; Source
0x18000643d  lea     rdi, [rsi+20h]
0x180006441  cmp     rbx, rbp
0x180006444  jz      short loc_180006480
0x180006446  test    r8, r8
0x180006449  jz      short loc_180006480
0x18000644b  cmp     [r8], r12b
0x18000644e  jz      short loc_180006480
0x180006450  inc     r15
0x180006453  cmp     [r8+r15], r12b
0x180006457  jnz     short loc_180006450
0x180006459  mov     rdx, rbp
0x18000645c  lea     r14, [r15+1]
0x180006460  sub     rdx, rbx; DestinationSize
0x180006463  cmp     rdx, r14
0x180006466  jb      short loc_180006480
0x180006468  mov     r9, r14; SourceSize
0x18000646b  mov     rcx, rbx; Destination
0x18000646e  call    memcpy_s
0x180006473  test    rdi, rdi
0x180006476  jz      short loc_18000647B
0x180006478  mov     [rdi], rbx
0x18000647b  add     rbx, r14
0x18000647e  jmp     short loc_180006488
0x180006480  test    rdi, rdi
0x180006483  jz      short loc_180006488
0x180006485  mov     [rdi], r12
0x180006488  mov     r8, [r13+18h]
0x18000648c  lea     r9, [rsi+38h]
0x180006490  mov     rdx, rbp
0x180006493  mov     rcx, rbx
0x180006496  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x18000649b  sub     rbp, rax
0x18000649e  xor     edx, edx; Val
0x1800064a0  mov     r8, rbp; Size
0x1800064a3  mov     rcx, rax; void *
0x1800064a6  call    memset
0x1800064ab  mov     rbx, [rsp+48h+arg_0]
0x1800064b0  mov     rbp, [rsp+48h+arg_8]
0x1800064b5  mov     rsi, [rsp+48h+arg_10]
0x1800064ba  add     rsp, 20h
0x1800064be  pop     r15
0x1800064c0  pop     r14
0x1800064c2  pop     r13
0x1800064c4  pop     r12
0x1800064c6  pop     rdi
0x1800064c7  retn
```

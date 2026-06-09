# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1400042b0`
- end: `0x1400044b0`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `512`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140004710`

## callees

- `0x140002ba0`
- `0x140002ea8`
- `0x1400042b0`
- `0x140005244`
- `0x140020760`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400043b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400043b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400043a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400043a3`

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
0x1400042b0  mov     [rsp+arg_0], rbx
0x1400042b5  mov     [rsp+arg_8], rbp
0x1400042ba  mov     [rsp+arg_10], rsi
0x1400042bf  push    rdi
0x1400042c0  push    r12
0x1400042c2  push    r13
0x1400042c4  push    r14
0x1400042c6  push    r15
0x1400042c8  sub     rsp, 20h
0x1400042cc  mov     [rcx+4], r8d
0x1400042d0  xor     r12d, r12d
0x1400042d3  mov     eax, [rdx+8]
0x1400042d6  mov     rsi, rcx
0x1400042d9  mov     [rcx+8], eax
0x1400042dc  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400042e0  mov     [rcx+10h], r12
0x1400042e4  mov     r13, rdx
0x1400042e7  movzx   eax, word ptr [rdx+40h]
0x1400042eb  mov     [rcx+18h], ax
0x1400042ef  mov     al, [rdx]
0x1400042f1  mov     [rcx+1Ah], al
0x1400042f4  mov     [rcx+20h], r12
0x1400042f8  mov     rax, [rdx+88h]
0x1400042ff  mov     [rcx+28h], rax
0x140004303  mov     rax, [rdx+90h]
0x14000430a  mov     [rcx+30h], rax
0x14000430e  mov     [rcx+38h], r12
0x140004312  mov     rcx, [rdx+38h]
0x140004316  lea     edx, [r12+1]
0x14000431b  test    rcx, rcx
0x14000431e  jnz     short loc_140004325
0x140004320  mov     r8d, edx
0x140004323  jmp     short loc_140004335
0x140004325  mov     rax, r15
0x140004328  inc     rax
0x14000432b  cmp     [rcx+rax], r12b
0x14000432f  jnz     short loc_140004328
0x140004331  lea     r8, [rax+1]; unsigned __int64
0x140004335  mov     rcx, [r13+80h]
0x14000433c  test    rcx, rcx
0x14000433f  jz      short loc_140004351
0x140004341  mov     rax, r15
0x140004344  inc     rax
0x140004347  cmp     [rcx+rax], r12b
0x14000434b  jnz     short loc_140004344
0x14000434d  lea     rdx, [rax+1]
0x140004351  mov     rcx, [r13+18h]
0x140004355  test    rcx, rcx
0x140004358  jnz     short loc_14000435F
0x14000435a  lea     eax, [rcx+2]
0x14000435d  jmp     short loc_140004374
0x14000435f  mov     rax, r15
0x140004362  inc     rax
0x140004365  cmp     [rcx+rax*2], r12w
0x14000436a  jnz     short loc_140004362
0x14000436c  lea     rax, ds:2[rax*2]
0x140004374  lea     rbp, [rax+rdx]
0x140004378  add     rbp, r8
0x14000437b  lea     rdi, [rsi+48h]
0x14000437f  cmp     [rsi+40h], r12
0x140004383  jz      short loc_14000438A
0x140004385  cmp     [rdi], rbp
0x140004388  jnb     short loc_1400043BE
0x14000438a  mov     rdx, rbp; dwBytes
0x14000438d  mov     ecx, 8; dwFlags
0x140004392  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004397  mov     r14, rax
0x14000439a  test    rax, rax
0x14000439d  jz      short loc_1400043BE
0x14000439f  mov     rbx, [rsi+40h]
0x1400043a3  call    cs:__imp_GetProcessHeap
0x1400043a9  mov     r8, rbx; lpMem
0x1400043ac  xor     edx, edx; dwFlags
0x1400043ae  mov     rcx, rax; hHeap
0x1400043b1  call    cs:__imp_HeapFree
0x1400043b7  mov     [rsi+40h], r14
0x1400043bb  mov     [rdi], rbp
0x1400043be  mov     rbx, [rsi+40h]
0x1400043c2  test    rbx, rbx
0x1400043c5  jz      loc_140004493
0x1400043cb  mov     rdx, [rdi]; DestinationSize
0x1400043ce  lea     rdi, [rsi+10h]
0x1400043d2  mov     r8, [r13+38h]; Source
0x1400043d6  lea     rbp, [rdx+rbx]
0x1400043da  cmp     rbx, rbp
0x1400043dd  jz      short loc_140004416
0x1400043df  test    r8, r8
0x1400043e2  jz      short loc_140004416
0x1400043e4  cmp     [r8], r12b
0x1400043e7  jz      short loc_140004416
0x1400043e9  mov     rax, r15
0x1400043ec  inc     rax
0x1400043ef  cmp     [r8+rax], r12b
0x1400043f3  jnz     short loc_1400043EC
0x1400043f5  lea     r14, [rax+1]
0x1400043f9  cmp     rdx, r14
0x1400043fc  jb      short loc_140004416
0x1400043fe  mov     r9, r14; SourceSize
0x140004401  mov     rcx, rbx; Destination
0x140004404  call    memcpy_s
0x140004409  test    rdi, rdi
0x14000440c  jz      short loc_140004411
0x14000440e  mov     [rdi], rbx
0x140004411  add     rbx, r14
0x140004414  jmp     short loc_14000441E
0x140004416  test    rdi, rdi
0x140004419  jz      short loc_14000441E
0x14000441b  mov     [rdi], r12
0x14000441e  mov     r8, [r13+80h]; Source
0x140004425  lea     rdi, [rsi+20h]
0x140004429  cmp     rbx, rbp
0x14000442c  jz      short loc_140004468
0x14000442e  test    r8, r8
0x140004431  jz      short loc_140004468
0x140004433  cmp     [r8], r12b
0x140004436  jz      short loc_140004468
0x140004438  inc     r15
0x14000443b  cmp     [r8+r15], r12b
0x14000443f  jnz     short loc_140004438
0x140004441  mov     rdx, rbp
0x140004444  lea     r14, [r15+1]
0x140004448  sub     rdx, rbx; DestinationSize
0x14000444b  cmp     rdx, r14
0x14000444e  jb      short loc_140004468
0x140004450  mov     r9, r14; SourceSize
0x140004453  mov     rcx, rbx; Destination
0x140004456  call    memcpy_s
0x14000445b  test    rdi, rdi
0x14000445e  jz      short loc_140004463
0x140004460  mov     [rdi], rbx
0x140004463  add     rbx, r14
0x140004466  jmp     short loc_140004470
0x140004468  test    rdi, rdi
0x14000446b  jz      short loc_140004470
0x14000446d  mov     [rdi], r12
0x140004470  mov     r8, [r13+18h]
0x140004474  lea     r9, [rsi+38h]
0x140004478  mov     rdx, rbp
0x14000447b  mov     rcx, rbx
0x14000447e  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x140004483  sub     rbp, rax
0x140004486  xor     edx, edx; Val
0x140004488  mov     r8, rbp; Size
0x14000448b  mov     rcx, rax; void *
0x14000448e  call    memset
0x140004493  mov     rbx, [rsp+48h+arg_0]
0x140004498  mov     rbp, [rsp+48h+arg_8]
0x14000449d  mov     rsi, [rsp+48h+arg_10]
0x1400044a2  add     rsp, 20h
0x1400044a6  pop     r15
0x1400044a8  pop     r14
0x1400044aa  pop     r13
0x1400044ac  pop     r12
0x1400044ae  pop     rdi
0x1400044af  retn
```

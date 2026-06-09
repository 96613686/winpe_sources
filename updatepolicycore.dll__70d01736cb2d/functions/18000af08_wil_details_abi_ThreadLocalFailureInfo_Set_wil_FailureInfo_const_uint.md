# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000af08`
- end: `0x18000b108`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `512`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b370`

## callees

- `0x180008d7c`
- `0x1800094bc`
- `0x18000af08`
- `0x18000b884`
- `0x18002fda9`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b009`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b009`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000affb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000affb`

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
    memset_0(v29, 0, v24 - v29);
  }
}

```

## disassembly

```asm
0x18000af08  mov     [rsp+arg_0], rbx
0x18000af0d  mov     [rsp+arg_8], rbp
0x18000af12  mov     [rsp+arg_10], rsi
0x18000af17  push    rdi
0x18000af18  push    r12
0x18000af1a  push    r13
0x18000af1c  push    r14
0x18000af1e  push    r15
0x18000af20  sub     rsp, 20h
0x18000af24  mov     [rcx+4], r8d
0x18000af28  xor     r12d, r12d
0x18000af2b  mov     eax, [rdx+8]
0x18000af2e  mov     rsi, rcx
0x18000af31  mov     [rcx+8], eax
0x18000af34  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000af38  mov     [rcx+10h], r12
0x18000af3c  mov     r13, rdx
0x18000af3f  movzx   eax, word ptr [rdx+40h]
0x18000af43  mov     [rcx+18h], ax
0x18000af47  mov     al, [rdx]
0x18000af49  mov     [rcx+1Ah], al
0x18000af4c  mov     [rcx+20h], r12
0x18000af50  mov     rax, [rdx+88h]
0x18000af57  mov     [rcx+28h], rax
0x18000af5b  mov     rax, [rdx+90h]
0x18000af62  mov     [rcx+30h], rax
0x18000af66  mov     [rcx+38h], r12
0x18000af6a  mov     rcx, [rdx+38h]
0x18000af6e  lea     edx, [r12+1]
0x18000af73  test    rcx, rcx
0x18000af76  jnz     short loc_18000AF7D
0x18000af78  mov     r8d, edx
0x18000af7b  jmp     short loc_18000AF8D
0x18000af7d  mov     rax, r15
0x18000af80  inc     rax
0x18000af83  cmp     [rcx+rax], r12b
0x18000af87  jnz     short loc_18000AF80
0x18000af89  lea     r8, [rax+1]; unsigned __int64
0x18000af8d  mov     rcx, [r13+80h]
0x18000af94  test    rcx, rcx
0x18000af97  jz      short loc_18000AFA9
0x18000af99  mov     rax, r15
0x18000af9c  inc     rax
0x18000af9f  cmp     [rcx+rax], r12b
0x18000afa3  jnz     short loc_18000AF9C
0x18000afa5  lea     rdx, [rax+1]
0x18000afa9  mov     rcx, [r13+18h]
0x18000afad  test    rcx, rcx
0x18000afb0  jnz     short loc_18000AFB7
0x18000afb2  lea     eax, [rcx+2]
0x18000afb5  jmp     short loc_18000AFCC
0x18000afb7  mov     rax, r15
0x18000afba  inc     rax
0x18000afbd  cmp     [rcx+rax*2], r12w
0x18000afc2  jnz     short loc_18000AFBA
0x18000afc4  lea     rax, ds:2[rax*2]
0x18000afcc  lea     rbp, [rax+rdx]
0x18000afd0  add     rbp, r8
0x18000afd3  lea     rdi, [rsi+48h]
0x18000afd7  cmp     [rsi+40h], r12
0x18000afdb  jz      short loc_18000AFE2
0x18000afdd  cmp     [rdi], rbp
0x18000afe0  jnb     short loc_18000B016
0x18000afe2  mov     rdx, rbp; dwBytes
0x18000afe5  mov     ecx, 8; dwFlags
0x18000afea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000afef  mov     r14, rax
0x18000aff2  test    rax, rax
0x18000aff5  jz      short loc_18000B016
0x18000aff7  mov     rbx, [rsi+40h]
0x18000affb  call    cs:__imp_GetProcessHeap
0x18000b001  mov     r8, rbx; lpMem
0x18000b004  xor     edx, edx; dwFlags
0x18000b006  mov     rcx, rax; hHeap
0x18000b009  call    cs:__imp_HeapFree
0x18000b00f  mov     [rsi+40h], r14
0x18000b013  mov     [rdi], rbp
0x18000b016  mov     rbx, [rsi+40h]
0x18000b01a  test    rbx, rbx
0x18000b01d  jz      loc_18000B0EB
0x18000b023  mov     rdx, [rdi]; DestinationSize
0x18000b026  lea     rdi, [rsi+10h]
0x18000b02a  mov     r8, [r13+38h]; Source
0x18000b02e  lea     rbp, [rdx+rbx]
0x18000b032  cmp     rbx, rbp
0x18000b035  jz      short loc_18000B06E
0x18000b037  test    r8, r8
0x18000b03a  jz      short loc_18000B06E
0x18000b03c  cmp     [r8], r12b
0x18000b03f  jz      short loc_18000B06E
0x18000b041  mov     rax, r15
0x18000b044  inc     rax
0x18000b047  cmp     [r8+rax], r12b
0x18000b04b  jnz     short loc_18000B044
0x18000b04d  lea     r14, [rax+1]
0x18000b051  cmp     rdx, r14
0x18000b054  jb      short loc_18000B06E
0x18000b056  mov     r9, r14; SourceSize
0x18000b059  mov     rcx, rbx; Destination
0x18000b05c  call    memcpy_s
0x18000b061  test    rdi, rdi
0x18000b064  jz      short loc_18000B069
0x18000b066  mov     [rdi], rbx
0x18000b069  add     rbx, r14
0x18000b06c  jmp     short loc_18000B076
0x18000b06e  test    rdi, rdi
0x18000b071  jz      short loc_18000B076
0x18000b073  mov     [rdi], r12
0x18000b076  mov     r8, [r13+80h]; Source
0x18000b07d  lea     rdi, [rsi+20h]
0x18000b081  cmp     rbx, rbp
0x18000b084  jz      short loc_18000B0C0
0x18000b086  test    r8, r8
0x18000b089  jz      short loc_18000B0C0
0x18000b08b  cmp     [r8], r12b
0x18000b08e  jz      short loc_18000B0C0
0x18000b090  inc     r15
0x18000b093  cmp     [r8+r15], r12b
0x18000b097  jnz     short loc_18000B090
0x18000b099  mov     rdx, rbp
0x18000b09c  lea     r14, [r15+1]
0x18000b0a0  sub     rdx, rbx; DestinationSize
0x18000b0a3  cmp     rdx, r14
0x18000b0a6  jb      short loc_18000B0C0
0x18000b0a8  mov     r9, r14; SourceSize
0x18000b0ab  mov     rcx, rbx; Destination
0x18000b0ae  call    memcpy_s
0x18000b0b3  test    rdi, rdi
0x18000b0b6  jz      short loc_18000B0BB
0x18000b0b8  mov     [rdi], rbx
0x18000b0bb  add     rbx, r14
0x18000b0be  jmp     short loc_18000B0C8
0x18000b0c0  test    rdi, rdi
0x18000b0c3  jz      short loc_18000B0C8
0x18000b0c5  mov     [rdi], r12
0x18000b0c8  mov     r8, [r13+18h]
0x18000b0cc  lea     r9, [rsi+38h]
0x18000b0d0  mov     rdx, rbp
0x18000b0d3  mov     rcx, rbx
0x18000b0d6  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x18000b0db  sub     rbp, rax
0x18000b0de  xor     edx, edx; Val
0x18000b0e0  mov     r8, rbp; Size
0x18000b0e3  mov     rcx, rax; void *
0x18000b0e6  call    memset_0
0x18000b0eb  mov     rbx, [rsp+48h+arg_0]
0x18000b0f0  mov     rbp, [rsp+48h+arg_8]
0x18000b0f5  mov     rsi, [rsp+48h+arg_10]
0x18000b0fa  add     rsp, 20h
0x18000b0fe  pop     r15
0x18000b100  pop     r14
0x18000b102  pop     r13
0x18000b104  pop     r12
0x18000b106  pop     rdi
0x18000b107  retn
```

# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180006864`
- end: `0x180006a64`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `512`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006cc0`

## callees

- `0x180004714`
- `0x180004dfc`
- `0x180006864`
- `0x180007154`
- `0x180047ab0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006965`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006965`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006957`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006957`

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
0x180006864  mov     [rsp+arg_0], rbx
0x180006869  mov     [rsp+arg_8], rbp
0x18000686e  mov     [rsp+arg_10], rsi
0x180006873  push    rdi
0x180006874  push    r12
0x180006876  push    r13
0x180006878  push    r14
0x18000687a  push    r15
0x18000687c  sub     rsp, 20h
0x180006880  mov     [rcx+4], r8d
0x180006884  xor     r12d, r12d
0x180006887  mov     eax, [rdx+8]
0x18000688a  mov     rsi, rcx
0x18000688d  mov     [rcx+8], eax
0x180006890  or      r15, 0FFFFFFFFFFFFFFFFh
0x180006894  mov     [rcx+10h], r12
0x180006898  mov     r13, rdx
0x18000689b  movzx   eax, word ptr [rdx+40h]
0x18000689f  mov     [rcx+18h], ax
0x1800068a3  mov     al, [rdx]
0x1800068a5  mov     [rcx+1Ah], al
0x1800068a8  mov     [rcx+20h], r12
0x1800068ac  mov     rax, [rdx+88h]
0x1800068b3  mov     [rcx+28h], rax
0x1800068b7  mov     rax, [rdx+90h]
0x1800068be  mov     [rcx+30h], rax
0x1800068c2  mov     [rcx+38h], r12
0x1800068c6  mov     rcx, [rdx+38h]
0x1800068ca  lea     edx, [r12+1]
0x1800068cf  test    rcx, rcx
0x1800068d2  jnz     short loc_1800068D9
0x1800068d4  mov     r8d, edx
0x1800068d7  jmp     short loc_1800068E9
0x1800068d9  mov     rax, r15
0x1800068dc  inc     rax
0x1800068df  cmp     [rcx+rax], r12b
0x1800068e3  jnz     short loc_1800068DC
0x1800068e5  lea     r8, [rax+1]; unsigned __int64
0x1800068e9  mov     rcx, [r13+80h]
0x1800068f0  test    rcx, rcx
0x1800068f3  jz      short loc_180006905
0x1800068f5  mov     rax, r15
0x1800068f8  inc     rax
0x1800068fb  cmp     [rcx+rax], r12b
0x1800068ff  jnz     short loc_1800068F8
0x180006901  lea     rdx, [rax+1]
0x180006905  mov     rcx, [r13+18h]
0x180006909  test    rcx, rcx
0x18000690c  jnz     short loc_180006913
0x18000690e  lea     eax, [rcx+2]
0x180006911  jmp     short loc_180006928
0x180006913  mov     rax, r15
0x180006916  inc     rax
0x180006919  cmp     [rcx+rax*2], r12w
0x18000691e  jnz     short loc_180006916
0x180006920  lea     rax, ds:2[rax*2]
0x180006928  lea     rbp, [rax+rdx]
0x18000692c  add     rbp, r8
0x18000692f  lea     rdi, [rsi+48h]
0x180006933  cmp     [rsi+40h], r12
0x180006937  jz      short loc_18000693E
0x180006939  cmp     [rdi], rbp
0x18000693c  jnb     short loc_180006972
0x18000693e  mov     rdx, rbp; dwBytes
0x180006941  mov     ecx, 8; dwFlags
0x180006946  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000694b  mov     r14, rax
0x18000694e  test    rax, rax
0x180006951  jz      short loc_180006972
0x180006953  mov     rbx, [rsi+40h]
0x180006957  call    cs:__imp_GetProcessHeap
0x18000695d  mov     r8, rbx; lpMem
0x180006960  xor     edx, edx; dwFlags
0x180006962  mov     rcx, rax; hHeap
0x180006965  call    cs:__imp_HeapFree
0x18000696b  mov     [rsi+40h], r14
0x18000696f  mov     [rdi], rbp
0x180006972  mov     rbx, [rsi+40h]
0x180006976  test    rbx, rbx
0x180006979  jz      loc_180006A47
0x18000697f  mov     rdx, [rdi]; DestinationSize
0x180006982  lea     rdi, [rsi+10h]
0x180006986  mov     r8, [r13+38h]; Source
0x18000698a  lea     rbp, [rdx+rbx]
0x18000698e  cmp     rbx, rbp
0x180006991  jz      short loc_1800069CA
0x180006993  test    r8, r8
0x180006996  jz      short loc_1800069CA
0x180006998  cmp     [r8], r12b
0x18000699b  jz      short loc_1800069CA
0x18000699d  mov     rax, r15
0x1800069a0  inc     rax
0x1800069a3  cmp     [r8+rax], r12b
0x1800069a7  jnz     short loc_1800069A0
0x1800069a9  lea     r14, [rax+1]
0x1800069ad  cmp     rdx, r14
0x1800069b0  jb      short loc_1800069CA
0x1800069b2  mov     r9, r14; SourceSize
0x1800069b5  mov     rcx, rbx; Destination
0x1800069b8  call    memcpy_s
0x1800069bd  test    rdi, rdi
0x1800069c0  jz      short loc_1800069C5
0x1800069c2  mov     [rdi], rbx
0x1800069c5  add     rbx, r14
0x1800069c8  jmp     short loc_1800069D2
0x1800069ca  test    rdi, rdi
0x1800069cd  jz      short loc_1800069D2
0x1800069cf  mov     [rdi], r12
0x1800069d2  mov     r8, [r13+80h]; Source
0x1800069d9  lea     rdi, [rsi+20h]
0x1800069dd  cmp     rbx, rbp
0x1800069e0  jz      short loc_180006A1C
0x1800069e2  test    r8, r8
0x1800069e5  jz      short loc_180006A1C
0x1800069e7  cmp     [r8], r12b
0x1800069ea  jz      short loc_180006A1C
0x1800069ec  inc     r15
0x1800069ef  cmp     [r8+r15], r12b
0x1800069f3  jnz     short loc_1800069EC
0x1800069f5  mov     rdx, rbp
0x1800069f8  lea     r14, [r15+1]
0x1800069fc  sub     rdx, rbx; DestinationSize
0x1800069ff  cmp     rdx, r14
0x180006a02  jb      short loc_180006A1C
0x180006a04  mov     r9, r14; SourceSize
0x180006a07  mov     rcx, rbx; Destination
0x180006a0a  call    memcpy_s
0x180006a0f  test    rdi, rdi
0x180006a12  jz      short loc_180006A17
0x180006a14  mov     [rdi], rbx
0x180006a17  add     rbx, r14
0x180006a1a  jmp     short loc_180006A24
0x180006a1c  test    rdi, rdi
0x180006a1f  jz      short loc_180006A24
0x180006a21  mov     [rdi], r12
0x180006a24  mov     r8, [r13+18h]
0x180006a28  lea     r9, [rsi+38h]
0x180006a2c  mov     rdx, rbp
0x180006a2f  mov     rcx, rbx
0x180006a32  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x180006a37  sub     rbp, rax
0x180006a3a  xor     edx, edx; Val
0x180006a3c  mov     r8, rbp; Size
0x180006a3f  mov     rcx, rax; void *
0x180006a42  call    memset
0x180006a47  mov     rbx, [rsp+48h+arg_0]
0x180006a4c  mov     rbp, [rsp+48h+arg_8]
0x180006a51  mov     rsi, [rsp+48h+arg_10]
0x180006a56  add     rsp, 20h
0x180006a5a  pop     r15
0x180006a5c  pop     r14
0x180006a5e  pop     r13
0x180006a60  pop     r12
0x180006a62  pop     rdi
0x180006a63  retn
```

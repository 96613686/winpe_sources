# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180003dd0`
- end: `0x180003fd0`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `512`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180004230`

## callees

- `0x180001ab4`
- `0x18000215c`
- `0x180003dd0`
- `0x1800044a4`
- `0x180015a30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ed1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ed1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ec3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003ec3`

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
0x180003dd0  mov     [rsp+arg_0], rbx
0x180003dd5  mov     [rsp+arg_8], rbp
0x180003dda  mov     [rsp+arg_10], rsi
0x180003ddf  push    rdi
0x180003de0  push    r12
0x180003de2  push    r13
0x180003de4  push    r14
0x180003de6  push    r15
0x180003de8  sub     rsp, 20h
0x180003dec  mov     [rcx+4], r8d
0x180003df0  xor     r12d, r12d
0x180003df3  mov     eax, [rdx+8]
0x180003df6  mov     rsi, rcx
0x180003df9  mov     [rcx+8], eax
0x180003dfc  or      r15, 0FFFFFFFFFFFFFFFFh
0x180003e00  mov     [rcx+10h], r12
0x180003e04  mov     r13, rdx
0x180003e07  movzx   eax, word ptr [rdx+40h]
0x180003e0b  mov     [rcx+18h], ax
0x180003e0f  mov     al, [rdx]
0x180003e11  mov     [rcx+1Ah], al
0x180003e14  mov     [rcx+20h], r12
0x180003e18  mov     rax, [rdx+88h]
0x180003e1f  mov     [rcx+28h], rax
0x180003e23  mov     rax, [rdx+90h]
0x180003e2a  mov     [rcx+30h], rax
0x180003e2e  mov     [rcx+38h], r12
0x180003e32  mov     rcx, [rdx+38h]
0x180003e36  lea     edx, [r12+1]
0x180003e3b  test    rcx, rcx
0x180003e3e  jnz     short loc_180003E45
0x180003e40  mov     r8d, edx
0x180003e43  jmp     short loc_180003E55
0x180003e45  mov     rax, r15
0x180003e48  inc     rax
0x180003e4b  cmp     [rcx+rax], r12b
0x180003e4f  jnz     short loc_180003E48
0x180003e51  lea     r8, [rax+1]; unsigned __int64
0x180003e55  mov     rcx, [r13+80h]
0x180003e5c  test    rcx, rcx
0x180003e5f  jz      short loc_180003E71
0x180003e61  mov     rax, r15
0x180003e64  inc     rax
0x180003e67  cmp     [rcx+rax], r12b
0x180003e6b  jnz     short loc_180003E64
0x180003e6d  lea     rdx, [rax+1]
0x180003e71  mov     rcx, [r13+18h]
0x180003e75  test    rcx, rcx
0x180003e78  jnz     short loc_180003E7F
0x180003e7a  lea     eax, [rcx+2]
0x180003e7d  jmp     short loc_180003E94
0x180003e7f  mov     rax, r15
0x180003e82  inc     rax
0x180003e85  cmp     [rcx+rax*2], r12w
0x180003e8a  jnz     short loc_180003E82
0x180003e8c  lea     rax, ds:2[rax*2]
0x180003e94  lea     rbp, [rax+rdx]
0x180003e98  add     rbp, r8
0x180003e9b  lea     rdi, [rsi+48h]
0x180003e9f  cmp     [rsi+40h], r12
0x180003ea3  jz      short loc_180003EAA
0x180003ea5  cmp     [rdi], rbp
0x180003ea8  jnb     short loc_180003EDE
0x180003eaa  mov     rdx, rbp; dwBytes
0x180003ead  mov     ecx, 8; dwFlags
0x180003eb2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003eb7  mov     r14, rax
0x180003eba  test    rax, rax
0x180003ebd  jz      short loc_180003EDE
0x180003ebf  mov     rbx, [rsi+40h]
0x180003ec3  call    cs:__imp_GetProcessHeap
0x180003ec9  mov     r8, rbx; lpMem
0x180003ecc  xor     edx, edx; dwFlags
0x180003ece  mov     rcx, rax; hHeap
0x180003ed1  call    cs:__imp_HeapFree
0x180003ed7  mov     [rsi+40h], r14
0x180003edb  mov     [rdi], rbp
0x180003ede  mov     rbx, [rsi+40h]
0x180003ee2  test    rbx, rbx
0x180003ee5  jz      loc_180003FB3
0x180003eeb  mov     rdx, [rdi]; DestinationSize
0x180003eee  lea     rdi, [rsi+10h]
0x180003ef2  mov     r8, [r13+38h]; Source
0x180003ef6  lea     rbp, [rdx+rbx]
0x180003efa  cmp     rbx, rbp
0x180003efd  jz      short loc_180003F36
0x180003eff  test    r8, r8
0x180003f02  jz      short loc_180003F36
0x180003f04  cmp     [r8], r12b
0x180003f07  jz      short loc_180003F36
0x180003f09  mov     rax, r15
0x180003f0c  inc     rax
0x180003f0f  cmp     [r8+rax], r12b
0x180003f13  jnz     short loc_180003F0C
0x180003f15  lea     r14, [rax+1]
0x180003f19  cmp     rdx, r14
0x180003f1c  jb      short loc_180003F36
0x180003f1e  mov     r9, r14; SourceSize
0x180003f21  mov     rcx, rbx; Destination
0x180003f24  call    memcpy_s
0x180003f29  test    rdi, rdi
0x180003f2c  jz      short loc_180003F31
0x180003f2e  mov     [rdi], rbx
0x180003f31  add     rbx, r14
0x180003f34  jmp     short loc_180003F3E
0x180003f36  test    rdi, rdi
0x180003f39  jz      short loc_180003F3E
0x180003f3b  mov     [rdi], r12
0x180003f3e  mov     r8, [r13+80h]; Source
0x180003f45  lea     rdi, [rsi+20h]
0x180003f49  cmp     rbx, rbp
0x180003f4c  jz      short loc_180003F88
0x180003f4e  test    r8, r8
0x180003f51  jz      short loc_180003F88
0x180003f53  cmp     [r8], r12b
0x180003f56  jz      short loc_180003F88
0x180003f58  inc     r15
0x180003f5b  cmp     [r8+r15], r12b
0x180003f5f  jnz     short loc_180003F58
0x180003f61  mov     rdx, rbp
0x180003f64  lea     r14, [r15+1]
0x180003f68  sub     rdx, rbx; DestinationSize
0x180003f6b  cmp     rdx, r14
0x180003f6e  jb      short loc_180003F88
0x180003f70  mov     r9, r14; SourceSize
0x180003f73  mov     rcx, rbx; Destination
0x180003f76  call    memcpy_s
0x180003f7b  test    rdi, rdi
0x180003f7e  jz      short loc_180003F83
0x180003f80  mov     [rdi], rbx
0x180003f83  add     rbx, r14
0x180003f86  jmp     short loc_180003F90
0x180003f88  test    rdi, rdi
0x180003f8b  jz      short loc_180003F90
0x180003f8d  mov     [rdi], r12
0x180003f90  mov     r8, [r13+18h]
0x180003f94  lea     r9, [rsi+38h]
0x180003f98  mov     rdx, rbp
0x180003f9b  mov     rcx, rbx
0x180003f9e  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x180003fa3  sub     rbp, rax
0x180003fa6  xor     edx, edx; Val
0x180003fa8  mov     r8, rbp; Size
0x180003fab  mov     rcx, rax; void *
0x180003fae  call    memset
0x180003fb3  mov     rbx, [rsp+48h+arg_0]
0x180003fb8  mov     rbp, [rsp+48h+arg_8]
0x180003fbd  mov     rsi, [rsp+48h+arg_10]
0x180003fc2  add     rsp, 20h
0x180003fc6  pop     r15
0x180003fc8  pop     r14
0x180003fca  pop     r13
0x180003fcc  pop     r12
0x180003fce  pop     rdi
0x180003fcf  retn
```

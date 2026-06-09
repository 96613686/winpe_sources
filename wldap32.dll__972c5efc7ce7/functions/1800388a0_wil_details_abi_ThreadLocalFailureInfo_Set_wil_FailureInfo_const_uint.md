# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800388a0`
- end: `0x180038a1d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `381`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180038b10`

## callees

- `0x18002a804`
- `0x180034e6c`
- `0x180035c78`
- `0x180037cd4`
- `0x180038534`
- `0x180038558`
- `0x1800388a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038948`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038948`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003895c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003895c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  _QWORD *v3; // rsi
  unsigned __int64 v6; // r15
  const char *v7; // rdx
  unsigned __int64 v8; // r15
  const char *v9; // rdx
  SIZE_T v10; // r15
  SIZE_T *v11; // rdi
  LPVOID v12; // r12
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  char *v16; // rdi
  void *v17; // rax
  const unsigned __int16 *v18; // rdx
  char *v19; // rbx
  wil::details *v20; // rcx
  rsize_t v21; // rax
  const void *v22; // rcx
  rsize_t v23; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (_QWORD *)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v8 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v7) + v6;
  v10 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v9) + v8;
  v11 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v11 < v10 )
  {
    v12 = wil::details::ProcessHeapAlloc(8u, v10);
    if ( v12 )
    {
      v13 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
      *((_QWORD *)this + 8) = v12;
      *v11 = v10;
    }
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = (void *)wil::details::WriteResultString<char const *>(v15);
    v19 = (char *)wil::details::WriteResultString<char const *>(v17);
    if ( v19 != v16
      && (v20 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v20
      && (v21 = wil::details::ResultStringSize(v20, v18), v23 = v21, v16 - v19 >= v21) )
    {
      memcpy_s(v19, v16 - v19, v22, v21);
      if ( v3 )
        *v3 = v19;
      v19 += v23;
    }
    else if ( v3 )
    {
      *v3 = 0;
    }
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x1800388a0  push    rbx
0x1800388a2  push    rbp
0x1800388a3  push    rsi
0x1800388a4  push    rdi
0x1800388a5  push    r12
0x1800388a7  push    r13
0x1800388a9  push    r14
0x1800388ab  push    r15
0x1800388ad  sub     rsp, 28h
0x1800388b1  mov     [rcx+4], r8d
0x1800388b5  lea     rbx, [rcx+20h]
0x1800388b9  mov     eax, [rdx+8]
0x1800388bc  lea     rsi, [rcx+38h]
0x1800388c0  mov     [rcx+8], eax
0x1800388c3  xor     r12d, r12d
0x1800388c6  mov     [rcx+10h], r12
0x1800388ca  mov     rbp, rcx
0x1800388cd  movzx   eax, word ptr [rdx+40h]
0x1800388d1  mov     r14, rdx
0x1800388d4  mov     [rcx+18h], ax
0x1800388d8  mov     al, [rdx]
0x1800388da  mov     [rcx+1Ah], al
0x1800388dd  mov     [rbx], r12
0x1800388e0  mov     rax, [rdx+88h]
0x1800388e7  mov     [rcx+28h], rax
0x1800388eb  mov     rax, [rdx+90h]
0x1800388f2  mov     [rcx+30h], rax
0x1800388f6  mov     [rsi], r12
0x1800388f9  mov     rcx, [rdx+18h]; this
0x1800388fd  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180038902  mov     rcx, [r14+38h]; this
0x180038906  mov     r15, rax
0x180038909  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18003890e  mov     rcx, [r14+80h]; this
0x180038915  add     r15, rax
0x180038918  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18003891d  add     r15, rax
0x180038920  lea     rdi, [rbp+48h]
0x180038924  cmp     [rbp+40h], r12
0x180038928  jz      short loc_18003892F
0x18003892a  cmp     [rdi], r15
0x18003892d  jnb     short loc_180038976
0x18003892f  mov     rdx, r15; dwBytes
0x180038932  mov     ecx, 8; dwFlags
0x180038937  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18003893c  mov     r12, rax
0x18003893f  test    rax, rax
0x180038942  jz      short loc_180038973
0x180038944  mov     rbx, [rbp+40h]
0x180038948  call    cs:__imp_GetProcessHeap
0x18003894f  nop     dword ptr [rax+rax+00h]
0x180038954  mov     r8, rbx; lpMem
0x180038957  xor     edx, edx; dwFlags
0x180038959  mov     rcx, rax; hHeap
0x18003895c  call    cs:__imp_HeapFree
0x180038963  nop     dword ptr [rax+rax+00h]
0x180038968  mov     [rbp+40h], r12
0x18003896c  lea     rbx, [rbp+20h]
0x180038970  mov     [rdi], r15
0x180038973  xor     r12d, r12d
0x180038976  mov     rcx, [rbp+40h]; Destination
0x18003897a  test    rcx, rcx
0x18003897d  jz      loc_180038A0B
0x180038983  mov     rdi, [rdi]
0x180038986  lea     r9, [rbp+10h]
0x18003898a  mov     r8, [r14+38h]
0x18003898e  add     rdi, rcx
0x180038991  mov     rdx, rdi
0x180038994  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180038999  mov     r8, [r14+80h]
0x1800389a0  mov     r9, rbx
0x1800389a3  mov     rdx, rdi
0x1800389a6  mov     rcx, rax; Destination
0x1800389a9  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800389ae  mov     rbx, rax
0x1800389b1  cmp     rax, rdi
0x1800389b4  jz      short loc_1800389F3
0x1800389b6  mov     rcx, [r14+18h]; this
0x1800389ba  test    rcx, rcx
0x1800389bd  jz      short loc_1800389F3
0x1800389bf  cmp     [rcx], r12w
0x1800389c3  jz      short loc_1800389F3
0x1800389c5  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800389ca  mov     rdx, rdi
0x1800389cd  mov     r14, rax
0x1800389d0  sub     rdx, rbx; DestinationSize
0x1800389d3  cmp     rdx, rax
0x1800389d6  jb      short loc_1800389F3
0x1800389d8  mov     r8, rcx; Source
0x1800389db  mov     r9, rax; SourceSize
0x1800389de  mov     rcx, rbx; Destination
0x1800389e1  call    memcpy_s
0x1800389e6  test    rsi, rsi
0x1800389e9  jz      short loc_1800389EE
0x1800389eb  mov     [rsi], rbx
0x1800389ee  add     rbx, r14
0x1800389f1  jmp     short loc_1800389FB
0x1800389f3  test    rsi, rsi
0x1800389f6  jz      short loc_1800389FB
0x1800389f8  mov     [rsi], r12
0x1800389fb  sub     rdi, rbx
0x1800389fe  xor     edx, edx; Val
0x180038a00  mov     r8, rdi; Size
0x180038a03  mov     rcx, rbx; void *
0x180038a06  call    memset_0
0x180038a0b  add     rsp, 28h
0x180038a0f  pop     r15
0x180038a11  pop     r14
0x180038a13  pop     r13
0x180038a15  pop     r12
0x180038a17  pop     rdi
0x180038a18  pop     rsi
0x180038a19  pop     rbp
0x180038a1a  pop     rbx
0x180038a1b  retn
```

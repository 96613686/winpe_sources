# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180018d00`
- end: `0x180018e36`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180019098`

## callees

- `0x180009004`
- `0x18000d470`
- `0x180016364`
- `0x1800163dc`
- `0x180018c0c`
- `0x180018c2c`
- `0x180018d00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018daf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018daf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018dbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018dbd`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int64 v5; // rbp
  const char *v6; // rdx
  unsigned __int64 v7; // rbp
  const char *v8; // rdx
  SIZE_T v9; // rbp
  SIZE_T *v10; // rdi
  LPVOID v11; // r14
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  char *v14; // rcx
  char *v15; // rbx
  void *v16; // rax
  void *v17; // rax
  void *v18; // rax

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v5 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v6) + v5;
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v8) + v7;
  v10 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v10 < v9 )
  {
    v11 = wil::details::ProcessHeapAlloc(8u, v9);
    if ( v11 )
    {
      v12 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
      *((_QWORD *)this + 8) = v11;
      *v10 = v9;
    }
  }
  v14 = (char *)*((_QWORD *)this + 8);
  if ( v14 )
  {
    v15 = &v14[*v10];
    v16 = (void *)wil::details::WriteResultString<char const *>(v14);
    v17 = (void *)wil::details::WriteResultString<char const *>(v16);
    v18 = (void *)wil::details::WriteResultString<unsigned short const *>(v17);
    memset_0(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x180018d00  push    rbx
0x180018d02  push    rbp
0x180018d03  push    rsi
0x180018d04  push    rdi
0x180018d05  push    r12
0x180018d07  push    r13
0x180018d09  push    r14
0x180018d0b  push    r15
0x180018d0d  sub     rsp, 28h
0x180018d11  mov     [rcx+4], r8d
0x180018d15  lea     r14, [rcx+38h]
0x180018d19  mov     eax, [rdx+8]
0x180018d1c  mov     rsi, rcx
0x180018d1f  mov     [rcx+8], eax
0x180018d22  mov     r15, rdx
0x180018d25  mov     qword ptr [rcx+10h], 0
0x180018d2d  movzx   eax, word ptr [rdx+40h]
0x180018d31  mov     [rcx+18h], ax
0x180018d35  mov     al, [rdx]
0x180018d37  mov     [rcx+1Ah], al
0x180018d3a  mov     qword ptr [rcx+20h], 0
0x180018d42  mov     rax, [rdx+88h]
0x180018d49  mov     [rcx+28h], rax
0x180018d4d  mov     rax, [rdx+90h]
0x180018d54  mov     [rcx+30h], rax
0x180018d58  mov     qword ptr [r14], 0
0x180018d5f  mov     rcx, [rdx+18h]; this
0x180018d63  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180018d68  mov     rcx, [r15+38h]; this
0x180018d6c  mov     rbp, rax
0x180018d6f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180018d74  mov     rcx, [r15+80h]; this
0x180018d7b  add     rbp, rax
0x180018d7e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180018d83  add     rbp, rax
0x180018d86  lea     rdi, [rsi+48h]
0x180018d8a  cmp     qword ptr [rsi+40h], 0
0x180018d8f  jz      short loc_180018D96
0x180018d91  cmp     [rdi], rbp
0x180018d94  jnb     short loc_180018DCE
0x180018d96  mov     rdx, rbp; dwBytes
0x180018d99  mov     ecx, 8; dwFlags
0x180018d9e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180018da3  mov     r14, rax
0x180018da6  test    rax, rax
0x180018da9  jz      short loc_180018DCA
0x180018dab  mov     rbx, [rsi+40h]
0x180018daf  call    cs:__imp_GetProcessHeap
0x180018db5  mov     r8, rbx; lpMem
0x180018db8  xor     edx, edx; dwFlags
0x180018dba  mov     rcx, rax; hHeap
0x180018dbd  call    cs:__imp_HeapFree
0x180018dc3  mov     [rsi+40h], r14
0x180018dc7  mov     [rdi], rbp
0x180018dca  lea     r14, [rsi+38h]
0x180018dce  mov     rcx, [rsi+40h]; Destination
0x180018dd2  test    rcx, rcx
0x180018dd5  jz      short loc_180018E25
0x180018dd7  mov     rbx, [rdi]
0x180018dda  lea     r9, [rsi+10h]
0x180018dde  mov     r8, [r15+38h]
0x180018de2  add     rbx, rcx
0x180018de5  mov     rdx, rbx
0x180018de8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180018ded  mov     r8, [r15+80h]
0x180018df4  lea     r9, [rsi+20h]
0x180018df8  mov     rdx, rbx
0x180018dfb  mov     rcx, rax; Destination
0x180018dfe  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180018e03  mov     r8, [r15+18h]
0x180018e07  mov     r9, r14
0x180018e0a  mov     rdx, rbx
0x180018e0d  mov     rcx, rax; Destination
0x180018e10  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180018e15  sub     rbx, rax
0x180018e18  xor     edx, edx; Val
0x180018e1a  mov     r8, rbx; Size
0x180018e1d  mov     rcx, rax; void *
0x180018e20  call    memset_0
0x180018e25  add     rsp, 28h
0x180018e29  pop     r15
0x180018e2b  pop     r14
0x180018e2d  pop     r13
0x180018e2f  pop     r12
0x180018e31  pop     rdi
0x180018e32  pop     rsi
0x180018e33  pop     rbp
0x180018e34  pop     rbx
0x180018e35  retn
```

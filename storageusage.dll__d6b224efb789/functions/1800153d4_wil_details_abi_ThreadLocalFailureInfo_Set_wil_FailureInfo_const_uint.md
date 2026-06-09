# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800153d4`
- end: `0x18001550a`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001576c`

## callees

- `0x180005c94`
- `0x18000e9d0`
- `0x18000ea48`
- `0x180014268`
- `0x180015238`
- `0x180015258`
- `0x1800153d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015491`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015491`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015483`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015483`

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
0x1800153d4  push    rbx
0x1800153d6  push    rbp
0x1800153d7  push    rsi
0x1800153d8  push    rdi
0x1800153d9  push    r12
0x1800153db  push    r13
0x1800153dd  push    r14
0x1800153df  push    r15
0x1800153e1  sub     rsp, 28h
0x1800153e5  mov     [rcx+4], r8d
0x1800153e9  lea     r14, [rcx+38h]
0x1800153ed  mov     eax, [rdx+8]
0x1800153f0  mov     rsi, rcx
0x1800153f3  mov     [rcx+8], eax
0x1800153f6  mov     r15, rdx
0x1800153f9  mov     qword ptr [rcx+10h], 0
0x180015401  movzx   eax, word ptr [rdx+40h]
0x180015405  mov     [rcx+18h], ax
0x180015409  mov     al, [rdx]
0x18001540b  mov     [rcx+1Ah], al
0x18001540e  mov     qword ptr [rcx+20h], 0
0x180015416  mov     rax, [rdx+88h]
0x18001541d  mov     [rcx+28h], rax
0x180015421  mov     rax, [rdx+90h]
0x180015428  mov     [rcx+30h], rax
0x18001542c  mov     qword ptr [r14], 0
0x180015433  mov     rcx, [rdx+18h]; this
0x180015437  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001543c  mov     rcx, [r15+38h]; this
0x180015440  mov     rbp, rax
0x180015443  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180015448  mov     rcx, [r15+80h]; this
0x18001544f  add     rbp, rax
0x180015452  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180015457  add     rbp, rax
0x18001545a  lea     rdi, [rsi+48h]
0x18001545e  cmp     qword ptr [rsi+40h], 0
0x180015463  jz      short loc_18001546A
0x180015465  cmp     [rdi], rbp
0x180015468  jnb     short loc_1800154A2
0x18001546a  mov     rdx, rbp; dwBytes
0x18001546d  mov     ecx, 8; dwFlags
0x180015472  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180015477  mov     r14, rax
0x18001547a  test    rax, rax
0x18001547d  jz      short loc_18001549E
0x18001547f  mov     rbx, [rsi+40h]
0x180015483  call    cs:__imp_GetProcessHeap
0x180015489  mov     r8, rbx; lpMem
0x18001548c  xor     edx, edx; dwFlags
0x18001548e  mov     rcx, rax; hHeap
0x180015491  call    cs:__imp_HeapFree
0x180015497  mov     [rsi+40h], r14
0x18001549b  mov     [rdi], rbp
0x18001549e  lea     r14, [rsi+38h]
0x1800154a2  mov     rcx, [rsi+40h]; Destination
0x1800154a6  test    rcx, rcx
0x1800154a9  jz      short loc_1800154F9
0x1800154ab  mov     rbx, [rdi]
0x1800154ae  lea     r9, [rsi+10h]
0x1800154b2  mov     r8, [r15+38h]
0x1800154b6  add     rbx, rcx
0x1800154b9  mov     rdx, rbx
0x1800154bc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800154c1  mov     r8, [r15+80h]
0x1800154c8  lea     r9, [rsi+20h]
0x1800154cc  mov     rdx, rbx
0x1800154cf  mov     rcx, rax; Destination
0x1800154d2  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800154d7  mov     r8, [r15+18h]
0x1800154db  mov     r9, r14
0x1800154de  mov     rdx, rbx
0x1800154e1  mov     rcx, rax; Destination
0x1800154e4  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800154e9  sub     rbx, rax
0x1800154ec  xor     edx, edx; Val
0x1800154ee  mov     r8, rbx; Size
0x1800154f1  mov     rcx, rax; void *
0x1800154f4  call    memset_0
0x1800154f9  add     rsp, 28h
0x1800154fd  pop     r15
0x1800154ff  pop     r14
0x180015501  pop     r13
0x180015503  pop     r12
0x180015505  pop     rdi
0x180015506  pop     rsi
0x180015507  pop     rbp
0x180015508  pop     rbx
0x180015509  retn
```

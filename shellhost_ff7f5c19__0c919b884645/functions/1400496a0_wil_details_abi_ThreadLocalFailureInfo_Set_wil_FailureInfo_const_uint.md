# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1400496a0`
- end: `0x1400497d6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140049b20`

## callees

- `0x14001062c`
- `0x140045484`
- `0x1400454fc`
- `0x14004868c`
- `0x140049550`
- `0x140049570`
- `0x1400496a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004974f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004974f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14004975d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14004975d`

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
0x1400496a0  push    rbx
0x1400496a2  push    rbp
0x1400496a3  push    rsi
0x1400496a4  push    rdi
0x1400496a5  push    r12
0x1400496a7  push    r13
0x1400496a9  push    r14
0x1400496ab  push    r15
0x1400496ad  sub     rsp, 28h
0x1400496b1  mov     [rcx+4], r8d
0x1400496b5  lea     r14, [rcx+38h]
0x1400496b9  mov     eax, [rdx+8]
0x1400496bc  mov     rsi, rcx
0x1400496bf  mov     [rcx+8], eax
0x1400496c2  mov     r15, rdx
0x1400496c5  mov     qword ptr [rcx+10h], 0
0x1400496cd  movzx   eax, word ptr [rdx+40h]
0x1400496d1  mov     [rcx+18h], ax
0x1400496d5  mov     al, [rdx]
0x1400496d7  mov     [rcx+1Ah], al
0x1400496da  mov     qword ptr [rcx+20h], 0
0x1400496e2  mov     rax, [rdx+88h]
0x1400496e9  mov     [rcx+28h], rax
0x1400496ed  mov     rax, [rdx+90h]
0x1400496f4  mov     [rcx+30h], rax
0x1400496f8  mov     qword ptr [r14], 0
0x1400496ff  mov     rcx, [rdx+18h]; this
0x140049703  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140049708  mov     rcx, [r15+38h]; this
0x14004970c  mov     rbp, rax
0x14004970f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140049714  mov     rcx, [r15+80h]; this
0x14004971b  add     rbp, rax
0x14004971e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140049723  add     rbp, rax
0x140049726  lea     rdi, [rsi+48h]
0x14004972a  cmp     qword ptr [rsi+40h], 0
0x14004972f  jz      short loc_140049736
0x140049731  cmp     [rdi], rbp
0x140049734  jnb     short loc_14004976E
0x140049736  mov     rdx, rbp; dwBytes
0x140049739  mov     ecx, 8; dwFlags
0x14004973e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140049743  mov     r14, rax
0x140049746  test    rax, rax
0x140049749  jz      short loc_14004976A
0x14004974b  mov     rbx, [rsi+40h]
0x14004974f  call    cs:__imp_GetProcessHeap
0x140049755  mov     r8, rbx; lpMem
0x140049758  xor     edx, edx; dwFlags
0x14004975a  mov     rcx, rax; hHeap
0x14004975d  call    cs:__imp_HeapFree
0x140049763  mov     [rsi+40h], r14
0x140049767  mov     [rdi], rbp
0x14004976a  lea     r14, [rsi+38h]
0x14004976e  mov     rcx, [rsi+40h]; Destination
0x140049772  test    rcx, rcx
0x140049775  jz      short loc_1400497C5
0x140049777  mov     rbx, [rdi]
0x14004977a  lea     r9, [rsi+10h]
0x14004977e  mov     r8, [r15+38h]
0x140049782  add     rbx, rcx
0x140049785  mov     rdx, rbx
0x140049788  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14004978d  mov     r8, [r15+80h]
0x140049794  lea     r9, [rsi+20h]
0x140049798  mov     rdx, rbx
0x14004979b  mov     rcx, rax; Destination
0x14004979e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1400497a3  mov     r8, [r15+18h]
0x1400497a7  mov     r9, r14
0x1400497aa  mov     rdx, rbx
0x1400497ad  mov     rcx, rax; Destination
0x1400497b0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1400497b5  sub     rbx, rax
0x1400497b8  xor     edx, edx; Val
0x1400497ba  mov     r8, rbx; Size
0x1400497bd  mov     rcx, rax; void *
0x1400497c0  call    memset_0
0x1400497c5  add     rsp, 28h
0x1400497c9  pop     r15
0x1400497cb  pop     r14
0x1400497cd  pop     r13
0x1400497cf  pop     r12
0x1400497d1  pop     rdi
0x1400497d2  pop     rsi
0x1400497d3  pop     rbp
0x1400497d4  pop     rbx
0x1400497d5  retn
```

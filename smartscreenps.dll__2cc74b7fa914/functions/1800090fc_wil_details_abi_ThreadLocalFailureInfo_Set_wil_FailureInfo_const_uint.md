# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800090fc`
- end: `0x180009232`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180009494`

## callees

- `0x180007328`
- `0x1800073a0`
- `0x180008c78`
- `0x180009018`
- `0x180009038`
- `0x1800090fc`
- `0x18000c370`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091b9`

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
    memset(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x1800090fc  push    rbx
0x1800090fe  push    rbp
0x1800090ff  push    rsi
0x180009100  push    rdi
0x180009101  push    r12
0x180009103  push    r13
0x180009105  push    r14
0x180009107  push    r15
0x180009109  sub     rsp, 28h
0x18000910d  mov     [rcx+4], r8d
0x180009111  lea     r14, [rcx+38h]
0x180009115  mov     eax, [rdx+8]
0x180009118  mov     rsi, rcx
0x18000911b  mov     [rcx+8], eax
0x18000911e  mov     r15, rdx
0x180009121  mov     qword ptr [rcx+10h], 0
0x180009129  movzx   eax, word ptr [rdx+40h]
0x18000912d  mov     [rcx+18h], ax
0x180009131  mov     al, [rdx]
0x180009133  mov     [rcx+1Ah], al
0x180009136  mov     qword ptr [rcx+20h], 0
0x18000913e  mov     rax, [rdx+88h]
0x180009145  mov     [rcx+28h], rax
0x180009149  mov     rax, [rdx+90h]
0x180009150  mov     [rcx+30h], rax
0x180009154  mov     qword ptr [r14], 0
0x18000915b  mov     rcx, [rdx+18h]; this
0x18000915f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180009164  mov     rcx, [r15+38h]; this
0x180009168  mov     rbp, rax
0x18000916b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180009170  mov     rcx, [r15+80h]; this
0x180009177  add     rbp, rax
0x18000917a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000917f  add     rbp, rax
0x180009182  lea     rdi, [rsi+48h]
0x180009186  cmp     qword ptr [rsi+40h], 0
0x18000918b  jz      short loc_180009192
0x18000918d  cmp     [rdi], rbp
0x180009190  jnb     short loc_1800091CA
0x180009192  mov     rdx, rbp; dwBytes
0x180009195  mov     ecx, 8; dwFlags
0x18000919a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000919f  mov     r14, rax
0x1800091a2  test    rax, rax
0x1800091a5  jz      short loc_1800091C6
0x1800091a7  mov     rbx, [rsi+40h]
0x1800091ab  call    cs:__imp_GetProcessHeap
0x1800091b1  mov     r8, rbx; lpMem
0x1800091b4  xor     edx, edx; dwFlags
0x1800091b6  mov     rcx, rax; hHeap
0x1800091b9  call    cs:__imp_HeapFree
0x1800091bf  mov     [rsi+40h], r14
0x1800091c3  mov     [rdi], rbp
0x1800091c6  lea     r14, [rsi+38h]
0x1800091ca  mov     rcx, [rsi+40h]; Destination
0x1800091ce  test    rcx, rcx
0x1800091d1  jz      short loc_180009221
0x1800091d3  mov     rbx, [rdi]
0x1800091d6  lea     r9, [rsi+10h]
0x1800091da  mov     r8, [r15+38h]
0x1800091de  add     rbx, rcx
0x1800091e1  mov     rdx, rbx
0x1800091e4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800091e9  mov     r8, [r15+80h]
0x1800091f0  lea     r9, [rsi+20h]
0x1800091f4  mov     rdx, rbx
0x1800091f7  mov     rcx, rax; Destination
0x1800091fa  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800091ff  mov     r8, [r15+18h]
0x180009203  mov     r9, r14
0x180009206  mov     rdx, rbx
0x180009209  mov     rcx, rax; Destination
0x18000920c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180009211  sub     rbx, rax
0x180009214  xor     edx, edx; Val
0x180009216  mov     r8, rbx; Size
0x180009219  mov     rcx, rax; void *
0x18000921c  call    memset
0x180009221  add     rsp, 28h
0x180009225  pop     r15
0x180009227  pop     r14
0x180009229  pop     r13
0x18000922b  pop     r12
0x18000922d  pop     rdi
0x18000922e  pop     rsi
0x18000922f  pop     rbp
0x180009230  pop     rbx
0x180009231  retn
```

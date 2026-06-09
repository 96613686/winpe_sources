# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000b9d0`
- end: `0x18000bb06`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000bd68`

## callees

- `0x180009018`
- `0x180009f08`
- `0x180009f80`
- `0x18000b550`
- `0x18000b8a8`
- `0x18000b8c8`
- `0x18000b9d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ba8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ba7f`

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
0x18000b9d0  push    rbx
0x18000b9d2  push    rbp
0x18000b9d3  push    rsi
0x18000b9d4  push    rdi
0x18000b9d5  push    r12
0x18000b9d7  push    r13
0x18000b9d9  push    r14
0x18000b9db  push    r15
0x18000b9dd  sub     rsp, 28h
0x18000b9e1  mov     [rcx+4], r8d
0x18000b9e5  lea     r14, [rcx+38h]
0x18000b9e9  mov     eax, [rdx+8]
0x18000b9ec  mov     rsi, rcx
0x18000b9ef  mov     [rcx+8], eax
0x18000b9f2  mov     r15, rdx
0x18000b9f5  mov     qword ptr [rcx+10h], 0
0x18000b9fd  movzx   eax, word ptr [rdx+40h]
0x18000ba01  mov     [rcx+18h], ax
0x18000ba05  mov     al, [rdx]
0x18000ba07  mov     [rcx+1Ah], al
0x18000ba0a  mov     qword ptr [rcx+20h], 0
0x18000ba12  mov     rax, [rdx+88h]
0x18000ba19  mov     [rcx+28h], rax
0x18000ba1d  mov     rax, [rdx+90h]
0x18000ba24  mov     [rcx+30h], rax
0x18000ba28  mov     qword ptr [r14], 0
0x18000ba2f  mov     rcx, [rdx+18h]; this
0x18000ba33  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000ba38  mov     rcx, [r15+38h]; this
0x18000ba3c  mov     rbp, rax
0x18000ba3f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000ba44  mov     rcx, [r15+80h]; this
0x18000ba4b  add     rbp, rax
0x18000ba4e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000ba53  add     rbp, rax
0x18000ba56  lea     rdi, [rsi+48h]
0x18000ba5a  cmp     qword ptr [rsi+40h], 0
0x18000ba5f  jz      short loc_18000BA66
0x18000ba61  cmp     [rdi], rbp
0x18000ba64  jnb     short loc_18000BA9E
0x18000ba66  mov     rdx, rbp; dwBytes
0x18000ba69  mov     ecx, 8; dwFlags
0x18000ba6e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000ba73  mov     r14, rax
0x18000ba76  test    rax, rax
0x18000ba79  jz      short loc_18000BA9A
0x18000ba7b  mov     rbx, [rsi+40h]
0x18000ba7f  call    cs:__imp_GetProcessHeap
0x18000ba85  mov     r8, rbx; lpMem
0x18000ba88  xor     edx, edx; dwFlags
0x18000ba8a  mov     rcx, rax; hHeap
0x18000ba8d  call    cs:__imp_HeapFree
0x18000ba93  mov     [rsi+40h], r14
0x18000ba97  mov     [rdi], rbp
0x18000ba9a  lea     r14, [rsi+38h]
0x18000ba9e  mov     rcx, [rsi+40h]; Destination
0x18000baa2  test    rcx, rcx
0x18000baa5  jz      short loc_18000BAF5
0x18000baa7  mov     rbx, [rdi]
0x18000baaa  lea     r9, [rsi+10h]
0x18000baae  mov     r8, [r15+38h]
0x18000bab2  add     rbx, rcx
0x18000bab5  mov     rdx, rbx
0x18000bab8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000babd  mov     r8, [r15+80h]
0x18000bac4  lea     r9, [rsi+20h]
0x18000bac8  mov     rdx, rbx
0x18000bacb  mov     rcx, rax; Destination
0x18000bace  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000bad3  mov     r8, [r15+18h]
0x18000bad7  mov     r9, r14
0x18000bada  mov     rdx, rbx
0x18000badd  mov     rcx, rax; Destination
0x18000bae0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000bae5  sub     rbx, rax
0x18000bae8  xor     edx, edx; Val
0x18000baea  mov     r8, rbx; Size
0x18000baed  mov     rcx, rax; void *
0x18000baf0  call    memset_0
0x18000baf5  add     rsp, 28h
0x18000baf9  pop     r15
0x18000bafb  pop     r14
0x18000bafd  pop     r13
0x18000baff  pop     r12
0x18000bb01  pop     rdi
0x18000bb02  pop     rsi
0x18000bb03  pop     rbp
0x18000bb04  pop     rbx
0x18000bb05  retn
```

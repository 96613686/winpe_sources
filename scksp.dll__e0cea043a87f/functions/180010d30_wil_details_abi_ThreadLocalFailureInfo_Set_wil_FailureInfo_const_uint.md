# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180010d30`
- end: `0x180010e66`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800111b8`

## callees

- `0x180009e82`
- `0x18000c4fc`
- `0x18000c574`
- `0x18000f800`
- `0x180010ba8`
- `0x180010bc8`
- `0x180010d30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010ded`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010ded`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010ddf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010ddf`

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
0x180010d30  push    rbx
0x180010d32  push    rbp
0x180010d33  push    rsi
0x180010d34  push    rdi
0x180010d35  push    r12
0x180010d37  push    r13
0x180010d39  push    r14
0x180010d3b  push    r15
0x180010d3d  sub     rsp, 28h
0x180010d41  mov     [rcx+4], r8d
0x180010d45  lea     r14, [rcx+38h]
0x180010d49  mov     eax, [rdx+8]
0x180010d4c  mov     rsi, rcx
0x180010d4f  mov     [rcx+8], eax
0x180010d52  mov     r15, rdx
0x180010d55  mov     qword ptr [rcx+10h], 0
0x180010d5d  movzx   eax, word ptr [rdx+40h]
0x180010d61  mov     [rcx+18h], ax
0x180010d65  mov     al, [rdx]
0x180010d67  mov     [rcx+1Ah], al
0x180010d6a  mov     qword ptr [rcx+20h], 0
0x180010d72  mov     rax, [rdx+88h]
0x180010d79  mov     [rcx+28h], rax
0x180010d7d  mov     rax, [rdx+90h]
0x180010d84  mov     [rcx+30h], rax
0x180010d88  mov     qword ptr [r14], 0
0x180010d8f  mov     rcx, [rdx+18h]; this
0x180010d93  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180010d98  mov     rcx, [r15+38h]; this
0x180010d9c  mov     rbp, rax
0x180010d9f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180010da4  mov     rcx, [r15+80h]; this
0x180010dab  add     rbp, rax
0x180010dae  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180010db3  add     rbp, rax
0x180010db6  lea     rdi, [rsi+48h]
0x180010dba  cmp     qword ptr [rsi+40h], 0
0x180010dbf  jz      short loc_180010DC6
0x180010dc1  cmp     [rdi], rbp
0x180010dc4  jnb     short loc_180010DFE
0x180010dc6  mov     rdx, rbp; dwBytes
0x180010dc9  mov     ecx, 8; dwFlags
0x180010dce  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010dd3  mov     r14, rax
0x180010dd6  test    rax, rax
0x180010dd9  jz      short loc_180010DFA
0x180010ddb  mov     rbx, [rsi+40h]
0x180010ddf  call    cs:__imp_GetProcessHeap
0x180010de5  mov     r8, rbx; lpMem
0x180010de8  xor     edx, edx; dwFlags
0x180010dea  mov     rcx, rax; hHeap
0x180010ded  call    cs:__imp_HeapFree
0x180010df3  mov     [rsi+40h], r14
0x180010df7  mov     [rdi], rbp
0x180010dfa  lea     r14, [rsi+38h]
0x180010dfe  mov     rcx, [rsi+40h]; Destination
0x180010e02  test    rcx, rcx
0x180010e05  jz      short loc_180010E55
0x180010e07  mov     rbx, [rdi]
0x180010e0a  lea     r9, [rsi+10h]
0x180010e0e  mov     r8, [r15+38h]
0x180010e12  add     rbx, rcx
0x180010e15  mov     rdx, rbx
0x180010e18  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180010e1d  mov     r8, [r15+80h]
0x180010e24  lea     r9, [rsi+20h]
0x180010e28  mov     rdx, rbx
0x180010e2b  mov     rcx, rax; Destination
0x180010e2e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180010e33  mov     r8, [r15+18h]
0x180010e37  mov     r9, r14
0x180010e3a  mov     rdx, rbx
0x180010e3d  mov     rcx, rax; Destination
0x180010e40  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180010e45  sub     rbx, rax
0x180010e48  xor     edx, edx; Val
0x180010e4a  mov     r8, rbx; Size
0x180010e4d  mov     rcx, rax; void *
0x180010e50  call    memset_0
0x180010e55  add     rsp, 28h
0x180010e59  pop     r15
0x180010e5b  pop     r14
0x180010e5d  pop     r13
0x180010e5f  pop     r12
0x180010e61  pop     rdi
0x180010e62  pop     rsi
0x180010e63  pop     rbp
0x180010e64  pop     rbx
0x180010e65  retn
```

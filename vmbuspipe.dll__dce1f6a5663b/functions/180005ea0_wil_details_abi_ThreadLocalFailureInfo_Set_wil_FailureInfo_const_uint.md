# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180005ea0`
- end: `0x180005fd6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180006238`

## callees

- `0x1800030ae`
- `0x180003b6c`
- `0x180003be4`
- `0x180005c00`
- `0x180005d38`
- `0x180005d58`
- `0x180005ea0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f4f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005f4f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005f5d`

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
0x180005ea0  push    rbx
0x180005ea2  push    rbp
0x180005ea3  push    rsi
0x180005ea4  push    rdi
0x180005ea5  push    r12
0x180005ea7  push    r13
0x180005ea9  push    r14
0x180005eab  push    r15
0x180005ead  sub     rsp, 28h
0x180005eb1  mov     [rcx+4], r8d
0x180005eb5  lea     r14, [rcx+38h]
0x180005eb9  mov     eax, [rdx+8]
0x180005ebc  mov     rsi, rcx
0x180005ebf  mov     [rcx+8], eax
0x180005ec2  mov     r15, rdx
0x180005ec5  mov     qword ptr [rcx+10h], 0
0x180005ecd  movzx   eax, word ptr [rdx+40h]
0x180005ed1  mov     [rcx+18h], ax
0x180005ed5  mov     al, [rdx]
0x180005ed7  mov     [rcx+1Ah], al
0x180005eda  mov     qword ptr [rcx+20h], 0
0x180005ee2  mov     rax, [rdx+88h]
0x180005ee9  mov     [rcx+28h], rax
0x180005eed  mov     rax, [rdx+90h]
0x180005ef4  mov     [rcx+30h], rax
0x180005ef8  mov     qword ptr [r14], 0
0x180005eff  mov     rcx, [rdx+18h]; this
0x180005f03  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180005f08  mov     rcx, [r15+38h]; this
0x180005f0c  mov     rbp, rax
0x180005f0f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005f14  mov     rcx, [r15+80h]; this
0x180005f1b  add     rbp, rax
0x180005f1e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180005f23  add     rbp, rax
0x180005f26  lea     rdi, [rsi+48h]
0x180005f2a  cmp     qword ptr [rsi+40h], 0
0x180005f2f  jz      short loc_180005F36
0x180005f31  cmp     [rdi], rbp
0x180005f34  jnb     short loc_180005F6E
0x180005f36  mov     rdx, rbp; dwBytes
0x180005f39  mov     ecx, 8; dwFlags
0x180005f3e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005f43  mov     r14, rax
0x180005f46  test    rax, rax
0x180005f49  jz      short loc_180005F6A
0x180005f4b  mov     rbx, [rsi+40h]
0x180005f4f  call    cs:__imp_GetProcessHeap
0x180005f55  mov     r8, rbx; lpMem
0x180005f58  xor     edx, edx; dwFlags
0x180005f5a  mov     rcx, rax; hHeap
0x180005f5d  call    cs:__imp_HeapFree
0x180005f63  mov     [rsi+40h], r14
0x180005f67  mov     [rdi], rbp
0x180005f6a  lea     r14, [rsi+38h]
0x180005f6e  mov     rcx, [rsi+40h]; Destination
0x180005f72  test    rcx, rcx
0x180005f75  jz      short loc_180005FC5
0x180005f77  mov     rbx, [rdi]
0x180005f7a  lea     r9, [rsi+10h]
0x180005f7e  mov     r8, [r15+38h]
0x180005f82  add     rbx, rcx
0x180005f85  mov     rdx, rbx
0x180005f88  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005f8d  mov     r8, [r15+80h]
0x180005f94  lea     r9, [rsi+20h]
0x180005f98  mov     rdx, rbx
0x180005f9b  mov     rcx, rax; Destination
0x180005f9e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180005fa3  mov     r8, [r15+18h]
0x180005fa7  mov     r9, r14
0x180005faa  mov     rdx, rbx
0x180005fad  mov     rcx, rax; Destination
0x180005fb0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180005fb5  sub     rbx, rax
0x180005fb8  xor     edx, edx; Val
0x180005fba  mov     r8, rbx; Size
0x180005fbd  mov     rcx, rax; void *
0x180005fc0  call    memset_0
0x180005fc5  add     rsp, 28h
0x180005fc9  pop     r15
0x180005fcb  pop     r14
0x180005fcd  pop     r13
0x180005fcf  pop     r12
0x180005fd1  pop     rdi
0x180005fd2  pop     rsi
0x180005fd3  pop     rbp
0x180005fd4  pop     rbx
0x180005fd5  retn
```

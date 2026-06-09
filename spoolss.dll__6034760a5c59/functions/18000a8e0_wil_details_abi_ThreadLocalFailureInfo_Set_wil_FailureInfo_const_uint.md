# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000a8e0`
- end: `0x18000aa16`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000ac78`

## callees

- `0x180005cac`
- `0x180006d94`
- `0x180006e0c`
- `0x1800096c8`
- `0x18000a2cc`
- `0x18000a2ec`
- `0x18000a8e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a99d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a99d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a98f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a98f`

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
0x18000a8e0  push    rbx
0x18000a8e2  push    rbp
0x18000a8e3  push    rsi
0x18000a8e4  push    rdi
0x18000a8e5  push    r12
0x18000a8e7  push    r13
0x18000a8e9  push    r14
0x18000a8eb  push    r15
0x18000a8ed  sub     rsp, 28h
0x18000a8f1  mov     [rcx+4], r8d
0x18000a8f5  lea     r14, [rcx+38h]
0x18000a8f9  mov     eax, [rdx+8]
0x18000a8fc  mov     rsi, rcx
0x18000a8ff  mov     [rcx+8], eax
0x18000a902  mov     r15, rdx
0x18000a905  mov     qword ptr [rcx+10h], 0
0x18000a90d  movzx   eax, word ptr [rdx+40h]
0x18000a911  mov     [rcx+18h], ax
0x18000a915  mov     al, [rdx]
0x18000a917  mov     [rcx+1Ah], al
0x18000a91a  mov     qword ptr [rcx+20h], 0
0x18000a922  mov     rax, [rdx+88h]
0x18000a929  mov     [rcx+28h], rax
0x18000a92d  mov     rax, [rdx+90h]
0x18000a934  mov     [rcx+30h], rax
0x18000a938  mov     qword ptr [r14], 0
0x18000a93f  mov     rcx, [rdx+18h]; this
0x18000a943  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000a948  mov     rcx, [r15+38h]; this
0x18000a94c  mov     rbp, rax
0x18000a94f  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000a954  mov     rcx, [r15+80h]; this
0x18000a95b  add     rbp, rax
0x18000a95e  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000a963  add     rbp, rax
0x18000a966  lea     rdi, [rsi+48h]
0x18000a96a  cmp     qword ptr [rsi+40h], 0
0x18000a96f  jz      short loc_18000A976
0x18000a971  cmp     [rdi], rbp
0x18000a974  jnb     short loc_18000A9AE
0x18000a976  mov     rdx, rbp; dwBytes
0x18000a979  mov     ecx, 8; dwFlags
0x18000a97e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000a983  mov     r14, rax
0x18000a986  test    rax, rax
0x18000a989  jz      short loc_18000A9AA
0x18000a98b  mov     rbx, [rsi+40h]
0x18000a98f  call    cs:__imp_GetProcessHeap
0x18000a995  mov     r8, rbx; lpMem
0x18000a998  xor     edx, edx; dwFlags
0x18000a99a  mov     rcx, rax; hHeap
0x18000a99d  call    cs:__imp_HeapFree
0x18000a9a3  mov     [rsi+40h], r14
0x18000a9a7  mov     [rdi], rbp
0x18000a9aa  lea     r14, [rsi+38h]
0x18000a9ae  mov     rcx, [rsi+40h]; Destination
0x18000a9b2  test    rcx, rcx
0x18000a9b5  jz      short loc_18000AA05
0x18000a9b7  mov     rbx, [rdi]
0x18000a9ba  lea     r9, [rsi+10h]
0x18000a9be  mov     r8, [r15+38h]
0x18000a9c2  add     rbx, rcx
0x18000a9c5  mov     rdx, rbx
0x18000a9c8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000a9cd  mov     r8, [r15+80h]
0x18000a9d4  lea     r9, [rsi+20h]
0x18000a9d8  mov     rdx, rbx
0x18000a9db  mov     rcx, rax; Destination
0x18000a9de  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000a9e3  mov     r8, [r15+18h]
0x18000a9e7  mov     r9, r14
0x18000a9ea  mov     rdx, rbx
0x18000a9ed  mov     rcx, rax; Destination
0x18000a9f0  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000a9f5  sub     rbx, rax
0x18000a9f8  xor     edx, edx; Val
0x18000a9fa  mov     r8, rbx; Size
0x18000a9fd  mov     rcx, rax; void *
0x18000aa00  call    memset_0
0x18000aa05  add     rsp, 28h
0x18000aa09  pop     r15
0x18000aa0b  pop     r14
0x18000aa0d  pop     r13
0x18000aa0f  pop     r12
0x18000aa11  pop     rdi
0x18000aa12  pop     rsi
0x18000aa13  pop     rbp
0x18000aa14  pop     rbx
0x18000aa15  retn
```

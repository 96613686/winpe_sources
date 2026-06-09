# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180010d80`
- end: `0x180010eb6`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180011208`

## callees

- `0x18000d258`
- `0x18000d2d0`
- `0x18000fe98`
- `0x180010bf8`
- `0x180010c18`
- `0x180010d80`
- `0x1800131a2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010e2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010e2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010e3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010e3d`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  unsigned __int16 **v3; // r14
  unsigned __int64 v6; // rbp
  const char *v7; // rdx
  unsigned __int64 v8; // rbp
  const char *v9; // rdx
  SIZE_T v10; // rbp
  SIZE_T *v11; // rdi
  LPVOID v12; // r14
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  const char *v16; // rbx
  char *v17; // rax
  unsigned __int16 *v18; // rax
  char *v19; // rax

  *((_DWORD *)this + 1) = a3;
  v3 = (unsigned __int16 **)((char *)this + 56);
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
    v3 = (unsigned __int16 **)((char *)this + 56);
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = wil::details::WriteResultString<char const *>(v15, v16, *((wil::details **)a2 + 7), (char **)this + 2);
    v18 = (unsigned __int16 *)wil::details::WriteResultString<char const *>(
                                v17,
                                v16,
                                *((wil::details **)a2 + 16),
                                (char **)this + 4);
    v19 = wil::details::WriteResultString<unsigned short const *>(
            v18,
            (const unsigned __int16 *)v16,
            *((wil::details **)a2 + 3),
            v3);
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x180010d80  push    rbx
0x180010d82  push    rbp
0x180010d83  push    rsi
0x180010d84  push    rdi
0x180010d85  push    r12
0x180010d87  push    r13
0x180010d89  push    r14
0x180010d8b  push    r15
0x180010d8d  sub     rsp, 28h
0x180010d91  mov     [rcx+4], r8d
0x180010d95  lea     r14, [rcx+38h]
0x180010d99  mov     eax, [rdx+8]
0x180010d9c  mov     rsi, rcx
0x180010d9f  mov     [rcx+8], eax
0x180010da2  mov     r15, rdx
0x180010da5  mov     qword ptr [rcx+10h], 0
0x180010dad  movzx   eax, word ptr [rdx+40h]
0x180010db1  mov     [rcx+18h], ax
0x180010db5  mov     al, [rdx]
0x180010db7  mov     [rcx+1Ah], al
0x180010dba  mov     qword ptr [rcx+20h], 0
0x180010dc2  mov     rax, [rdx+88h]
0x180010dc9  mov     [rcx+28h], rax
0x180010dcd  mov     rax, [rdx+90h]
0x180010dd4  mov     [rcx+30h], rax
0x180010dd8  mov     qword ptr [r14], 0
0x180010ddf  mov     rcx, [rdx+18h]; this
0x180010de3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180010de8  mov     rcx, [r15+38h]; this
0x180010dec  mov     rbp, rax
0x180010def  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180010df4  mov     rcx, [r15+80h]; this
0x180010dfb  add     rbp, rax
0x180010dfe  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180010e03  add     rbp, rax
0x180010e06  lea     rdi, [rsi+48h]
0x180010e0a  cmp     qword ptr [rsi+40h], 0
0x180010e0f  jz      short loc_180010E16
0x180010e11  cmp     [rdi], rbp
0x180010e14  jnb     short loc_180010E4E
0x180010e16  mov     rdx, rbp; dwBytes
0x180010e19  mov     ecx, 8; dwFlags
0x180010e1e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180010e23  mov     r14, rax
0x180010e26  test    rax, rax
0x180010e29  jz      short loc_180010E4A
0x180010e2b  mov     rbx, [rsi+40h]
0x180010e2f  call    cs:__imp_GetProcessHeap
0x180010e35  mov     r8, rbx; lpMem
0x180010e38  xor     edx, edx; dwFlags
0x180010e3a  mov     rcx, rax; hHeap
0x180010e3d  call    cs:__imp_HeapFree
0x180010e43  mov     [rsi+40h], r14
0x180010e47  mov     [rdi], rbp
0x180010e4a  lea     r14, [rsi+38h]
0x180010e4e  mov     rcx, [rsi+40h]; Destination
0x180010e52  test    rcx, rcx
0x180010e55  jz      short loc_180010EA5
0x180010e57  mov     rbx, [rdi]
0x180010e5a  lea     r9, [rsi+10h]
0x180010e5e  mov     r8, [r15+38h]
0x180010e62  add     rbx, rcx
0x180010e65  mov     rdx, rbx
0x180010e68  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180010e6d  mov     r8, [r15+80h]
0x180010e74  lea     r9, [rsi+20h]
0x180010e78  mov     rdx, rbx
0x180010e7b  mov     rcx, rax; Destination
0x180010e7e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180010e83  mov     r8, [r15+18h]
0x180010e87  mov     r9, r14
0x180010e8a  mov     rdx, rbx
0x180010e8d  mov     rcx, rax; Destination
0x180010e90  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180010e95  sub     rbx, rax
0x180010e98  xor     edx, edx; Val
0x180010e9a  mov     r8, rbx; Size
0x180010e9d  mov     rcx, rax; void *
0x180010ea0  call    memset_0
0x180010ea5  add     rsp, 28h
0x180010ea9  pop     r15
0x180010eab  pop     r14
0x180010ead  pop     r13
0x180010eaf  pop     r12
0x180010eb1  pop     rdi
0x180010eb2  pop     rsi
0x180010eb3  pop     rbp
0x180010eb4  pop     rbx
0x180010eb5  retn
```

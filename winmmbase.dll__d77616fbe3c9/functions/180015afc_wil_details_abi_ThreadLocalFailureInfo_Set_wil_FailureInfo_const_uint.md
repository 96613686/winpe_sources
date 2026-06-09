# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180015afc`
- end: `0x180015c32`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180015e94`

## callees

- `0x18001102a`
- `0x180013710`
- `0x180013788`
- `0x18001541c`
- `0x180015a18`
- `0x180015a38`
- `0x180015afc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015bab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015bab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015bb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015bb9`

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
0x180015afc  push    rbx
0x180015afe  push    rbp
0x180015aff  push    rsi
0x180015b00  push    rdi
0x180015b01  push    r12
0x180015b03  push    r13
0x180015b05  push    r14
0x180015b07  push    r15
0x180015b09  sub     rsp, 28h
0x180015b0d  mov     [rcx+4], r8d
0x180015b11  lea     r14, [rcx+38h]
0x180015b15  mov     eax, [rdx+8]
0x180015b18  mov     rsi, rcx
0x180015b1b  mov     [rcx+8], eax
0x180015b1e  mov     r15, rdx
0x180015b21  mov     qword ptr [rcx+10h], 0
0x180015b29  movzx   eax, word ptr [rdx+40h]
0x180015b2d  mov     [rcx+18h], ax
0x180015b31  mov     al, [rdx]
0x180015b33  mov     [rcx+1Ah], al
0x180015b36  mov     qword ptr [rcx+20h], 0
0x180015b3e  mov     rax, [rdx+88h]
0x180015b45  mov     [rcx+28h], rax
0x180015b49  mov     rax, [rdx+90h]
0x180015b50  mov     [rcx+30h], rax
0x180015b54  mov     qword ptr [r14], 0
0x180015b5b  mov     rcx, [rdx+18h]; this
0x180015b5f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180015b64  mov     rcx, [r15+38h]; this
0x180015b68  mov     rbp, rax
0x180015b6b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180015b70  mov     rcx, [r15+80h]; this
0x180015b77  add     rbp, rax
0x180015b7a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180015b7f  add     rbp, rax
0x180015b82  lea     rdi, [rsi+48h]
0x180015b86  cmp     qword ptr [rsi+40h], 0
0x180015b8b  jz      short loc_180015B92
0x180015b8d  cmp     [rdi], rbp
0x180015b90  jnb     short loc_180015BCA
0x180015b92  mov     rdx, rbp; dwBytes
0x180015b95  mov     ecx, 8; dwFlags
0x180015b9a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180015b9f  mov     r14, rax
0x180015ba2  test    rax, rax
0x180015ba5  jz      short loc_180015BC6
0x180015ba7  mov     rbx, [rsi+40h]
0x180015bab  call    cs:__imp_GetProcessHeap
0x180015bb1  mov     r8, rbx; lpMem
0x180015bb4  xor     edx, edx; dwFlags
0x180015bb6  mov     rcx, rax; hHeap
0x180015bb9  call    cs:__imp_HeapFree
0x180015bbf  mov     [rsi+40h], r14
0x180015bc3  mov     [rdi], rbp
0x180015bc6  lea     r14, [rsi+38h]
0x180015bca  mov     rcx, [rsi+40h]; Destination
0x180015bce  test    rcx, rcx
0x180015bd1  jz      short loc_180015C21
0x180015bd3  mov     rbx, [rdi]
0x180015bd6  lea     r9, [rsi+10h]
0x180015bda  mov     r8, [r15+38h]
0x180015bde  add     rbx, rcx
0x180015be1  mov     rdx, rbx
0x180015be4  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180015be9  mov     r8, [r15+80h]
0x180015bf0  lea     r9, [rsi+20h]
0x180015bf4  mov     rdx, rbx
0x180015bf7  mov     rcx, rax; Destination
0x180015bfa  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180015bff  mov     r8, [r15+18h]
0x180015c03  mov     r9, r14
0x180015c06  mov     rdx, rbx
0x180015c09  mov     rcx, rax; Destination
0x180015c0c  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180015c11  sub     rbx, rax
0x180015c14  xor     edx, edx; Val
0x180015c16  mov     r8, rbx; Size
0x180015c19  mov     rcx, rax; void *
0x180015c1c  call    memset_0
0x180015c21  add     rsp, 28h
0x180015c25  pop     r15
0x180015c27  pop     r14
0x180015c29  pop     r13
0x180015c2b  pop     r12
0x180015c2d  pop     rdi
0x180015c2e  pop     rsi
0x180015c2f  pop     rbp
0x180015c30  pop     rbx
0x180015c31  retn
```

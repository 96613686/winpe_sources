# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009bd4`
- end: `0x180009d45`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180009d4c`

## callees

- `0x1800085a8`
- `0x180009900`
- `0x180009ab8`
- `0x180009ad8`
- `0x180009bd4`
- `0x18000f9da`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009d09`
- `msvcrt!memcpy_s` at `0x180009d09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c7c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c7c`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  char **v3; // rbx
  char **v4; // rsi
  unsigned __int64 v7; // r15
  const char *v8; // rdx
  unsigned __int64 v9; // r15
  const char *v10; // rdx
  SIZE_T v11; // r15
  SIZE_T *v12; // rdi
  LPVOID v13; // r12
  void *v14; // rbx
  HANDLE ProcessHeap; // rax
  char *v16; // rcx
  const char *v17; // rdi
  char *v18; // rax
  const unsigned __int16 *v19; // rdx
  char *v20; // rbx
  wil::details *v21; // rcx
  rsize_t v22; // rax
  const void *v23; // rcx
  rsize_t v24; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (char **)((char *)this + 32);
  v4 = (char **)((char *)this + 56);
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v7 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const unsigned __int16 *)a2);
  v9 = wil::details::ResultStringSize(*((wil::details **)a2 + 7), v8) + v7;
  v11 = wil::details::ResultStringSize(*((wil::details **)a2 + 16), v10) + v9;
  v12 = (SIZE_T *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v12 < v11 )
  {
    v13 = wil::details::ProcessHeapAlloc(8u, v11);
    if ( v13 )
    {
      v14 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v14);
      *((_QWORD *)this + 8) = v13;
      v3 = (char **)((char *)this + 32);
      *v12 = v11;
    }
  }
  v16 = (char *)*((_QWORD *)this + 8);
  if ( v16 )
  {
    v17 = &v16[*v12];
    v18 = wil::details::WriteResultString<char const *>(v16, v17, *((wil::details **)a2 + 7), (char **)this + 2);
    v20 = wil::details::WriteResultString<char const *>(v18, v17, *((wil::details **)a2 + 16), v3);
    if ( v20 != v17
      && (v21 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v21
      && (v22 = wil::details::ResultStringSize(v21, v19), v24 = v22, v17 - v20 >= v22) )
    {
      memcpy_s(v20, v17 - v20, v23, v22);
      if ( v4 )
        *v4 = v20;
      v20 += v24;
    }
    else if ( v4 )
    {
      *v4 = 0;
    }
    memset_0(v20, 0, v17 - v20);
  }
}

```

## disassembly

```asm
0x180009bd4  push    rbx
0x180009bd6  push    rbp
0x180009bd7  push    rsi
0x180009bd8  push    rdi
0x180009bd9  push    r12
0x180009bdb  push    r13
0x180009bdd  push    r14
0x180009bdf  push    r15
0x180009be1  sub     rsp, 28h
0x180009be5  mov     [rcx+4], r8d
0x180009be9  lea     rbx, [rcx+20h]
0x180009bed  mov     eax, [rdx+8]
0x180009bf0  lea     rsi, [rcx+38h]
0x180009bf4  mov     [rcx+8], eax
0x180009bf7  xor     r12d, r12d
0x180009bfa  mov     [rcx+10h], r12
0x180009bfe  mov     rbp, rcx
0x180009c01  movzx   eax, word ptr [rdx+40h]
0x180009c05  mov     r14, rdx
0x180009c08  mov     [rcx+18h], ax
0x180009c0c  mov     al, [rdx]
0x180009c0e  mov     [rcx+1Ah], al
0x180009c11  mov     [rbx], r12
0x180009c14  mov     rax, [rdx+88h]
0x180009c1b  mov     [rcx+28h], rax
0x180009c1f  mov     rax, [rdx+90h]
0x180009c26  mov     [rcx+30h], rax
0x180009c2a  mov     [rsi], r12
0x180009c2d  mov     rcx, [rdx+18h]; this
0x180009c31  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180009c36  mov     rcx, [r14+38h]; this
0x180009c3a  mov     r15, rax
0x180009c3d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180009c42  mov     rcx, [r14+80h]; this
0x180009c49  add     r15, rax
0x180009c4c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180009c51  add     r15, rax
0x180009c54  lea     rdi, [rbp+48h]
0x180009c58  cmp     [rbp+40h], r12
0x180009c5c  jz      short loc_180009C63
0x180009c5e  cmp     [rdi], r15
0x180009c61  jnb     short loc_180009C9E
0x180009c63  mov     rdx, r15; dwBytes
0x180009c66  mov     ecx, 8; dwFlags
0x180009c6b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009c70  mov     r12, rax
0x180009c73  test    rax, rax
0x180009c76  jz      short loc_180009C9B
0x180009c78  mov     rbx, [rbp+40h]
0x180009c7c  call    cs:__imp_GetProcessHeap
0x180009c82  mov     r8, rbx; lpMem
0x180009c85  xor     edx, edx; dwFlags
0x180009c87  mov     rcx, rax; hHeap
0x180009c8a  call    cs:__imp_HeapFree
0x180009c90  mov     [rbp+40h], r12
0x180009c94  lea     rbx, [rbp+20h]
0x180009c98  mov     [rdi], r15
0x180009c9b  xor     r12d, r12d
0x180009c9e  mov     rcx, [rbp+40h]; Destination
0x180009ca2  test    rcx, rcx
0x180009ca5  jz      loc_180009D34
0x180009cab  mov     rdi, [rdi]
0x180009cae  lea     r9, [rbp+10h]
0x180009cb2  mov     r8, [r14+38h]
0x180009cb6  add     rdi, rcx
0x180009cb9  mov     rdx, rdi
0x180009cbc  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009cc1  mov     r8, [r14+80h]
0x180009cc8  mov     r9, rbx
0x180009ccb  mov     rdx, rdi
0x180009cce  mov     rcx, rax; Destination
0x180009cd1  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009cd6  mov     rbx, rax
0x180009cd9  cmp     rax, rdi
0x180009cdc  jz      short loc_180009D1C
0x180009cde  mov     rcx, [r14+18h]; this
0x180009ce2  test    rcx, rcx
0x180009ce5  jz      short loc_180009D1C
0x180009ce7  cmp     [rcx], r12w
0x180009ceb  jz      short loc_180009D1C
0x180009ced  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180009cf2  mov     rdx, rdi
0x180009cf5  mov     r14, rax
0x180009cf8  sub     rdx, rbx; DestinationSize
0x180009cfb  cmp     rdx, rax
0x180009cfe  jb      short loc_180009D1C
0x180009d00  mov     r8, rcx; Source
0x180009d03  mov     r9, rax; SourceSize
0x180009d06  mov     rcx, rbx; Destination
0x180009d09  call    cs:__imp_memcpy_s
0x180009d0f  test    rsi, rsi
0x180009d12  jz      short loc_180009D17
0x180009d14  mov     [rsi], rbx
0x180009d17  add     rbx, r14
0x180009d1a  jmp     short loc_180009D24
0x180009d1c  test    rsi, rsi
0x180009d1f  jz      short loc_180009D24
0x180009d21  mov     [rsi], r12
0x180009d24  sub     rdi, rbx
0x180009d27  xor     edx, edx; Val
0x180009d29  mov     r8, rdi; Size
0x180009d2c  mov     rcx, rbx; void *
0x180009d2f  call    memset_0
0x180009d34  add     rsp, 28h
0x180009d38  pop     r15
0x180009d3a  pop     r14
0x180009d3c  pop     r13
0x180009d3e  pop     r12
0x180009d40  pop     rdi
0x180009d41  pop     rsi
0x180009d42  pop     rbp
0x180009d43  pop     rbx
0x180009d44  retn
```

# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18003a99c`
- end: `0x18003ab0c`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003acb8`

## callees

- `0x180001ee8`
- `0x180033204`
- `0x180039630`
- `0x18003a8d4`
- `0x18003a8f4`
- `0x18003a99c`
- `0x18003c2cc`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18003aa52`
- `KERNEL32!HeapFree` at `0x18003aa52`
- `KERNEL32!GetProcessHeap` at `0x18003aa44`
- `KERNEL32!GetProcessHeap` at `0x18003aa44`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  _QWORD *v3; // rsi
  unsigned __int64 v6; // r15
  const char *v7; // rdx
  unsigned __int64 v8; // r15
  const char *v9; // rdx
  SIZE_T v10; // r15
  SIZE_T *v11; // rdi
  LPVOID v12; // r12
  void *v13; // rbx
  HANDLE ProcessHeap; // rax
  char *v15; // rcx
  char *v16; // rdi
  void *v17; // rax
  const unsigned __int16 *v18; // rdx
  char *v19; // rbx
  wil::details *v20; // rcx
  rsize_t v21; // rax
  const void *v22; // rcx
  rsize_t v23; // r14

  *((_DWORD *)this + 1) = a3;
  v3 = (_QWORD *)((char *)this + 56);
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
  }
  v15 = (char *)*((_QWORD *)this + 8);
  if ( v15 )
  {
    v16 = &v15[*v11];
    v17 = (void *)wil::details::WriteResultString<char const *>(v15);
    v19 = (char *)wil::details::WriteResultString<char const *>(v17);
    if ( v19 != v16
      && (v20 = (wil::details *)*((_QWORD *)a2 + 3)) != 0
      && *(_WORD *)v20
      && (v21 = wil::details::ResultStringSize(v20, v18), v23 = v21, v16 - v19 >= v21) )
    {
      memcpy_s(v19, v16 - v19, v22, v21);
      if ( v3 )
        *v3 = v19;
      v19 += v23;
    }
    else if ( v3 )
    {
      *v3 = 0;
    }
    memset_0(v19, 0, v16 - v19);
  }
}

```

## disassembly

```asm
0x18003a99c  push    rbx
0x18003a99e  push    rbp
0x18003a99f  push    rsi
0x18003a9a0  push    rdi
0x18003a9a1  push    r12
0x18003a9a3  push    r13
0x18003a9a5  push    r14
0x18003a9a7  push    r15
0x18003a9a9  sub     rsp, 28h
0x18003a9ad  mov     [rcx+4], r8d
0x18003a9b1  lea     rbx, [rcx+20h]
0x18003a9b5  mov     eax, [rdx+8]
0x18003a9b8  lea     rsi, [rcx+38h]
0x18003a9bc  mov     [rcx+8], eax
0x18003a9bf  xor     r12d, r12d
0x18003a9c2  mov     [rcx+10h], r12
0x18003a9c6  mov     rbp, rcx
0x18003a9c9  movzx   eax, word ptr [rdx+40h]
0x18003a9cd  mov     r14, rdx
0x18003a9d0  mov     [rcx+18h], ax
0x18003a9d4  mov     al, [rdx]
0x18003a9d6  mov     [rcx+1Ah], al
0x18003a9d9  mov     [rbx], r12
0x18003a9dc  mov     rax, [rdx+88h]
0x18003a9e3  mov     [rcx+28h], rax
0x18003a9e7  mov     rax, [rdx+90h]
0x18003a9ee  mov     [rcx+30h], rax
0x18003a9f2  mov     [rsi], r12
0x18003a9f5  mov     rcx, [rdx+18h]; this
0x18003a9f9  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18003a9fe  mov     rcx, [r14+38h]; this
0x18003aa02  mov     r15, rax
0x18003aa05  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18003aa0a  mov     rcx, [r14+80h]; this
0x18003aa11  add     r15, rax
0x18003aa14  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18003aa19  add     r15, rax
0x18003aa1c  lea     rdi, [rbp+48h]
0x18003aa20  cmp     [rbp+40h], r12
0x18003aa24  jz      short loc_18003AA2B
0x18003aa26  cmp     [rdi], r15
0x18003aa29  jnb     short loc_18003AA66
0x18003aa2b  mov     rdx, r15; dwBytes
0x18003aa2e  mov     ecx, 8; dwFlags
0x18003aa33  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18003aa38  mov     r12, rax
0x18003aa3b  test    rax, rax
0x18003aa3e  jz      short loc_18003AA63
0x18003aa40  mov     rbx, [rbp+40h]
0x18003aa44  call    cs:__imp_GetProcessHeap
0x18003aa4a  mov     r8, rbx; lpMem
0x18003aa4d  xor     edx, edx; dwFlags
0x18003aa4f  mov     rcx, rax; hHeap
0x18003aa52  call    cs:__imp_HeapFree
0x18003aa58  mov     [rbp+40h], r12
0x18003aa5c  lea     rbx, [rbp+20h]
0x18003aa60  mov     [rdi], r15
0x18003aa63  xor     r12d, r12d
0x18003aa66  mov     rcx, [rbp+40h]; Destination
0x18003aa6a  test    rcx, rcx
0x18003aa6d  jz      loc_18003AAFB
0x18003aa73  mov     rdi, [rdi]
0x18003aa76  lea     r9, [rbp+10h]
0x18003aa7a  mov     r8, [r14+38h]
0x18003aa7e  add     rdi, rcx
0x18003aa81  mov     rdx, rdi
0x18003aa84  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18003aa89  mov     r8, [r14+80h]
0x18003aa90  mov     r9, rbx
0x18003aa93  mov     rdx, rdi
0x18003aa96  mov     rcx, rax; Destination
0x18003aa99  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18003aa9e  mov     rbx, rax
0x18003aaa1  cmp     rax, rdi
0x18003aaa4  jz      short loc_18003AAE3
0x18003aaa6  mov     rcx, [r14+18h]; this
0x18003aaaa  test    rcx, rcx
0x18003aaad  jz      short loc_18003AAE3
0x18003aaaf  cmp     [rcx], r12w
0x18003aab3  jz      short loc_18003AAE3
0x18003aab5  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18003aaba  mov     rdx, rdi
0x18003aabd  mov     r14, rax
0x18003aac0  sub     rdx, rbx; DestinationSize
0x18003aac3  cmp     rdx, rax
0x18003aac6  jb      short loc_18003AAE3
0x18003aac8  mov     r8, rcx; Source
0x18003aacb  mov     r9, rax; SourceSize
0x18003aace  mov     rcx, rbx; Destination
0x18003aad1  call    memcpy_s
0x18003aad6  test    rsi, rsi
0x18003aad9  jz      short loc_18003AADE
0x18003aadb  mov     [rsi], rbx
0x18003aade  add     rbx, r14
0x18003aae1  jmp     short loc_18003AAEB
0x18003aae3  test    rsi, rsi
0x18003aae6  jz      short loc_18003AAEB
0x18003aae8  mov     [rsi], r12
0x18003aaeb  sub     rdi, rbx
0x18003aaee  xor     edx, edx; Val
0x18003aaf0  mov     r8, rdi; Size
0x18003aaf3  mov     rcx, rbx; void *
0x18003aaf6  call    memset_0
0x18003aafb  add     rsp, 28h
0x18003aaff  pop     r15
0x18003ab01  pop     r14
0x18003ab03  pop     r13
0x18003ab05  pop     r12
0x18003ab07  pop     rdi
0x18003ab08  pop     rsi
0x18003ab09  pop     rbp
0x18003ab0a  pop     rbx
0x18003ab0b  retn
```

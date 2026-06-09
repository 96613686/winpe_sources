# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001f3b4`
- end: `0x18001f525`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001f52c`

## callees

- `0x180013d60`
- `0x18001de04`
- `0x18001f324`
- `0x18001f344`
- `0x18001f3b4`
- `0x18002205f`

## import_xrefs

- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18001f4e9`
- `api-ms-win-core-crt-l1-1-0!memcpy_s` at `0x18001f4e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f46a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001f46a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f45c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001f45c`

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
0x18001f3b4  push    rbx
0x18001f3b6  push    rbp
0x18001f3b7  push    rsi
0x18001f3b8  push    rdi
0x18001f3b9  push    r12
0x18001f3bb  push    r13
0x18001f3bd  push    r14
0x18001f3bf  push    r15
0x18001f3c1  sub     rsp, 28h
0x18001f3c5  mov     [rcx+4], r8d
0x18001f3c9  lea     rbx, [rcx+20h]
0x18001f3cd  mov     eax, [rdx+8]
0x18001f3d0  lea     rsi, [rcx+38h]
0x18001f3d4  mov     [rcx+8], eax
0x18001f3d7  xor     r12d, r12d
0x18001f3da  mov     [rcx+10h], r12
0x18001f3de  mov     rbp, rcx
0x18001f3e1  movzx   eax, word ptr [rdx+40h]
0x18001f3e5  mov     r14, rdx
0x18001f3e8  mov     [rcx+18h], ax
0x18001f3ec  mov     al, [rdx]
0x18001f3ee  mov     [rcx+1Ah], al
0x18001f3f1  mov     [rbx], r12
0x18001f3f4  mov     rax, [rdx+88h]
0x18001f3fb  mov     [rcx+28h], rax
0x18001f3ff  mov     rax, [rdx+90h]
0x18001f406  mov     [rcx+30h], rax
0x18001f40a  mov     [rsi], r12
0x18001f40d  mov     rcx, [rdx+18h]; this
0x18001f411  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001f416  mov     rcx, [r14+38h]; this
0x18001f41a  mov     r15, rax
0x18001f41d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001f422  mov     rcx, [r14+80h]; this
0x18001f429  add     r15, rax
0x18001f42c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001f431  add     r15, rax
0x18001f434  lea     rdi, [rbp+48h]
0x18001f438  cmp     [rbp+40h], r12
0x18001f43c  jz      short loc_18001F443
0x18001f43e  cmp     [rdi], r15
0x18001f441  jnb     short loc_18001F47E
0x18001f443  mov     rdx, r15; dwBytes
0x18001f446  mov     ecx, 8; dwFlags
0x18001f44b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001f450  mov     r12, rax
0x18001f453  test    rax, rax
0x18001f456  jz      short loc_18001F47B
0x18001f458  mov     rbx, [rbp+40h]
0x18001f45c  call    cs:__imp_GetProcessHeap
0x18001f462  mov     r8, rbx; lpMem
0x18001f465  xor     edx, edx; dwFlags
0x18001f467  mov     rcx, rax; hHeap
0x18001f46a  call    cs:__imp_HeapFree
0x18001f470  mov     [rbp+40h], r12
0x18001f474  lea     rbx, [rbp+20h]
0x18001f478  mov     [rdi], r15
0x18001f47b  xor     r12d, r12d
0x18001f47e  mov     rcx, [rbp+40h]; Destination
0x18001f482  test    rcx, rcx
0x18001f485  jz      loc_18001F514
0x18001f48b  mov     rdi, [rdi]
0x18001f48e  lea     r9, [rbp+10h]
0x18001f492  mov     r8, [r14+38h]
0x18001f496  add     rdi, rcx
0x18001f499  mov     rdx, rdi
0x18001f49c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001f4a1  mov     r8, [r14+80h]
0x18001f4a8  mov     r9, rbx
0x18001f4ab  mov     rdx, rdi
0x18001f4ae  mov     rcx, rax; Destination
0x18001f4b1  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001f4b6  mov     rbx, rax
0x18001f4b9  cmp     rax, rdi
0x18001f4bc  jz      short loc_18001F4FC
0x18001f4be  mov     rcx, [r14+18h]; this
0x18001f4c2  test    rcx, rcx
0x18001f4c5  jz      short loc_18001F4FC
0x18001f4c7  cmp     [rcx], r12w
0x18001f4cb  jz      short loc_18001F4FC
0x18001f4cd  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001f4d2  mov     rdx, rdi
0x18001f4d5  mov     r14, rax
0x18001f4d8  sub     rdx, rbx; DestinationSize
0x18001f4db  cmp     rdx, rax
0x18001f4de  jb      short loc_18001F4FC
0x18001f4e0  mov     r8, rcx; Source
0x18001f4e3  mov     r9, rax; SourceSize
0x18001f4e6  mov     rcx, rbx; Destination
0x18001f4e9  call    cs:__imp_memcpy_s
0x18001f4ef  test    rsi, rsi
0x18001f4f2  jz      short loc_18001F4F7
0x18001f4f4  mov     [rsi], rbx
0x18001f4f7  add     rbx, r14
0x18001f4fa  jmp     short loc_18001F504
0x18001f4fc  test    rsi, rsi
0x18001f4ff  jz      short loc_18001F504
0x18001f501  mov     [rsi], r12
0x18001f504  sub     rdi, rbx
0x18001f507  xor     edx, edx; Val
0x18001f509  mov     r8, rdi; Size
0x18001f50c  mov     rcx, rbx; void *
0x18001f50f  call    memset_0
0x18001f514  add     rsp, 28h
0x18001f518  pop     r15
0x18001f51a  pop     r14
0x18001f51c  pop     r13
0x18001f51e  pop     r12
0x18001f520  pop     rdi
0x18001f521  pop     rsi
0x18001f522  pop     rbp
0x18001f523  pop     rbx
0x18001f524  retn
```

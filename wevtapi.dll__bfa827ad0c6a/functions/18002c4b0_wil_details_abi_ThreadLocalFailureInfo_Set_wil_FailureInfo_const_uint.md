# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18002c4b0`
- end: `0x18002c620`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `368`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002c714`

## callees

- `0x1800209cc`
- `0x180025514`
- `0x180029908`
- `0x18002bb20`
- `0x18002c33c`
- `0x18002c35c`
- `0x18002c4b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c558`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c558`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c566`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c566`

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
  const wchar_t *v18; // rdx
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
  v6 = wil::details::ResultStringSize(*((wil::details **)a2 + 3), (const wchar_t *)a2);
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
0x18002c4b0  push    rbx
0x18002c4b2  push    rbp
0x18002c4b3  push    rsi
0x18002c4b4  push    rdi
0x18002c4b5  push    r12
0x18002c4b7  push    r13
0x18002c4b9  push    r14
0x18002c4bb  push    r15
0x18002c4bd  sub     rsp, 28h
0x18002c4c1  mov     [rcx+4], r8d
0x18002c4c5  lea     rbx, [rcx+20h]
0x18002c4c9  mov     eax, [rdx+8]
0x18002c4cc  lea     rsi, [rcx+38h]
0x18002c4d0  mov     [rcx+8], eax
0x18002c4d3  xor     r12d, r12d
0x18002c4d6  mov     [rcx+10h], r12
0x18002c4da  mov     rbp, rcx
0x18002c4dd  movzx   eax, word ptr [rdx+40h]
0x18002c4e1  mov     r14, rdx
0x18002c4e4  mov     [rcx+18h], ax
0x18002c4e8  mov     al, [rdx]
0x18002c4ea  mov     [rcx+1Ah], al
0x18002c4ed  mov     [rbx], r12
0x18002c4f0  mov     rax, [rdx+88h]
0x18002c4f7  mov     [rcx+28h], rax
0x18002c4fb  mov     rax, [rdx+90h]
0x18002c502  mov     [rcx+30h], rax
0x18002c506  mov     [rsi], r12
0x18002c509  mov     rcx, [rdx+18h]; this
0x18002c50d  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x18002c512  mov     rcx, [r14+38h]; this
0x18002c516  mov     r15, rax
0x18002c519  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002c51e  mov     rcx, [r14+80h]; this
0x18002c525  add     r15, rax
0x18002c528  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002c52d  add     r15, rax
0x18002c530  lea     rdi, [rbp+48h]
0x18002c534  cmp     [rbp+40h], r12
0x18002c538  jz      short loc_18002C53F
0x18002c53a  cmp     [rdi], r15
0x18002c53d  jnb     short loc_18002C57A
0x18002c53f  mov     rdx, r15; dwBytes
0x18002c542  mov     ecx, 8; dwFlags
0x18002c547  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002c54c  mov     r12, rax
0x18002c54f  test    rax, rax
0x18002c552  jz      short loc_18002C577
0x18002c554  mov     rbx, [rbp+40h]
0x18002c558  call    cs:__imp_GetProcessHeap
0x18002c55e  mov     r8, rbx; lpMem
0x18002c561  xor     edx, edx; dwFlags
0x18002c563  mov     rcx, rax; hHeap
0x18002c566  call    cs:__imp_HeapFree
0x18002c56c  mov     [rbp+40h], r12
0x18002c570  lea     rbx, [rbp+20h]
0x18002c574  mov     [rdi], r15
0x18002c577  xor     r12d, r12d
0x18002c57a  mov     rcx, [rbp+40h]; Destination
0x18002c57e  test    rcx, rcx
0x18002c581  jz      loc_18002C60F
0x18002c587  mov     rdi, [rdi]
0x18002c58a  lea     r9, [rbp+10h]
0x18002c58e  mov     r8, [r14+38h]
0x18002c592  add     rdi, rcx
0x18002c595  mov     rdx, rdi
0x18002c598  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002c59d  mov     r8, [r14+80h]
0x18002c5a4  mov     r9, rbx
0x18002c5a7  mov     rdx, rdi
0x18002c5aa  mov     rcx, rax; Destination
0x18002c5ad  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002c5b2  mov     rbx, rax
0x18002c5b5  cmp     rax, rdi
0x18002c5b8  jz      short loc_18002C5F7
0x18002c5ba  mov     rcx, [r14+18h]; this
0x18002c5be  test    rcx, rcx
0x18002c5c1  jz      short loc_18002C5F7
0x18002c5c3  cmp     [rcx], r12w
0x18002c5c7  jz      short loc_18002C5F7
0x18002c5c9  call    ?ResultStringSize@details@wil@@YA_KPEB_W@Z; wil::details::ResultStringSize(wchar_t const *)
0x18002c5ce  mov     rdx, rdi
0x18002c5d1  mov     r14, rax
0x18002c5d4  sub     rdx, rbx; DestinationSize
0x18002c5d7  cmp     rdx, rax
0x18002c5da  jb      short loc_18002C5F7
0x18002c5dc  mov     r8, rcx; Source
0x18002c5df  mov     r9, rax; SourceSize
0x18002c5e2  mov     rcx, rbx; Destination
0x18002c5e5  call    memcpy_s
0x18002c5ea  test    rsi, rsi
0x18002c5ed  jz      short loc_18002C5F2
0x18002c5ef  mov     [rsi], rbx
0x18002c5f2  add     rbx, r14
0x18002c5f5  jmp     short loc_18002C5FF
0x18002c5f7  test    rsi, rsi
0x18002c5fa  jz      short loc_18002C5FF
0x18002c5fc  mov     [rsi], r12
0x18002c5ff  sub     rdi, rbx
0x18002c602  xor     edx, edx; Val
0x18002c604  mov     r8, rdi; Size
0x18002c607  mov     rcx, rbx; void *
0x18002c60a  call    memset_0
0x18002c60f  add     rsp, 28h
0x18002c613  pop     r15
0x18002c615  pop     r14
0x18002c617  pop     r13
0x18002c619  pop     r12
0x18002c61b  pop     rdi
0x18002c61c  pop     rsi
0x18002c61d  pop     rbp
0x18002c61e  pop     rbx
0x18002c61f  retn
```

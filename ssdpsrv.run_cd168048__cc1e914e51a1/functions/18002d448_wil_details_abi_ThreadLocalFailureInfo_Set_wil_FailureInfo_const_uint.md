# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18002d448`
- end: `0x18002d5c5`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `381`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002d6b8`

## callees

- `0x180029104`
- `0x18002911c`
- `0x18002a590`
- `0x18002c7f4`
- `0x18002d2c4`
- `0x18002d2e8`
- `0x18002d448`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d504`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d504`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d4f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d4f0`

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
0x18002d448  push    rbx
0x18002d44a  push    rbp
0x18002d44b  push    rsi
0x18002d44c  push    rdi
0x18002d44d  push    r12
0x18002d44f  push    r13
0x18002d451  push    r14
0x18002d453  push    r15
0x18002d455  sub     rsp, 28h
0x18002d459  mov     [rcx+4], r8d
0x18002d45d  lea     rbx, [rcx+20h]
0x18002d461  mov     eax, [rdx+8]
0x18002d464  lea     rsi, [rcx+38h]
0x18002d468  mov     [rcx+8], eax
0x18002d46b  xor     r12d, r12d
0x18002d46e  mov     [rcx+10h], r12
0x18002d472  mov     rbp, rcx
0x18002d475  movzx   eax, word ptr [rdx+40h]
0x18002d479  mov     r14, rdx
0x18002d47c  mov     [rcx+18h], ax
0x18002d480  mov     al, [rdx]
0x18002d482  mov     [rcx+1Ah], al
0x18002d485  mov     [rbx], r12
0x18002d488  mov     rax, [rdx+88h]
0x18002d48f  mov     [rcx+28h], rax
0x18002d493  mov     rax, [rdx+90h]
0x18002d49a  mov     [rcx+30h], rax
0x18002d49e  mov     [rsi], r12
0x18002d4a1  mov     rcx, [rdx+18h]; this
0x18002d4a5  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18002d4aa  mov     rcx, [r14+38h]; this
0x18002d4ae  mov     r15, rax
0x18002d4b1  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002d4b6  mov     rcx, [r14+80h]; this
0x18002d4bd  add     r15, rax
0x18002d4c0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002d4c5  add     r15, rax
0x18002d4c8  lea     rdi, [rbp+48h]
0x18002d4cc  cmp     [rbp+40h], r12
0x18002d4d0  jz      short loc_18002D4D7
0x18002d4d2  cmp     [rdi], r15
0x18002d4d5  jnb     short loc_18002D51E
0x18002d4d7  mov     rdx, r15; dwBytes
0x18002d4da  mov     ecx, 8; dwFlags
0x18002d4df  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002d4e4  mov     r12, rax
0x18002d4e7  test    rax, rax
0x18002d4ea  jz      short loc_18002D51B
0x18002d4ec  mov     rbx, [rbp+40h]
0x18002d4f0  call    cs:__imp_GetProcessHeap
0x18002d4f7  nop     dword ptr [rax+rax+00h]
0x18002d4fc  mov     r8, rbx; lpMem
0x18002d4ff  xor     edx, edx; dwFlags
0x18002d501  mov     rcx, rax; hHeap
0x18002d504  call    cs:__imp_HeapFree
0x18002d50b  nop     dword ptr [rax+rax+00h]
0x18002d510  mov     [rbp+40h], r12
0x18002d514  lea     rbx, [rbp+20h]
0x18002d518  mov     [rdi], r15
0x18002d51b  xor     r12d, r12d
0x18002d51e  mov     rcx, [rbp+40h]; Destination
0x18002d522  test    rcx, rcx
0x18002d525  jz      loc_18002D5B3
0x18002d52b  mov     rdi, [rdi]
0x18002d52e  lea     r9, [rbp+10h]
0x18002d532  mov     r8, [r14+38h]
0x18002d536  add     rdi, rcx
0x18002d539  mov     rdx, rdi
0x18002d53c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002d541  mov     r8, [r14+80h]
0x18002d548  mov     r9, rbx
0x18002d54b  mov     rdx, rdi
0x18002d54e  mov     rcx, rax; Destination
0x18002d551  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002d556  mov     rbx, rax
0x18002d559  cmp     rax, rdi
0x18002d55c  jz      short loc_18002D59B
0x18002d55e  mov     rcx, [r14+18h]; this
0x18002d562  test    rcx, rcx
0x18002d565  jz      short loc_18002D59B
0x18002d567  cmp     [rcx], r12w
0x18002d56b  jz      short loc_18002D59B
0x18002d56d  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18002d572  mov     rdx, rdi
0x18002d575  mov     r14, rax
0x18002d578  sub     rdx, rbx; DestinationSize
0x18002d57b  cmp     rdx, rax
0x18002d57e  jb      short loc_18002D59B
0x18002d580  mov     r8, rcx; Source
0x18002d583  mov     r9, rax; SourceSize
0x18002d586  mov     rcx, rbx; Destination
0x18002d589  call    memcpy_s
0x18002d58e  test    rsi, rsi
0x18002d591  jz      short loc_18002D596
0x18002d593  mov     [rsi], rbx
0x18002d596  add     rbx, r14
0x18002d599  jmp     short loc_18002D5A3
0x18002d59b  test    rsi, rsi
0x18002d59e  jz      short loc_18002D5A3
0x18002d5a0  mov     [rsi], r12
0x18002d5a3  sub     rdi, rbx
0x18002d5a6  xor     edx, edx; Val
0x18002d5a8  mov     r8, rdi; Size
0x18002d5ab  mov     rcx, rbx; void *
0x18002d5ae  call    memset_0
0x18002d5b3  add     rsp, 28h
0x18002d5b7  pop     r15
0x18002d5b9  pop     r14
0x18002d5bb  pop     r13
0x18002d5bd  pop     r12
0x18002d5bf  pop     rdi
0x18002d5c0  pop     rsi
0x18002d5c1  pop     rbp
0x18002d5c2  pop     rbx
0x18002d5c3  retn
```

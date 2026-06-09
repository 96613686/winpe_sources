# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000e01c`
- end: `0x18000e18d`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000e194`

## callees

- `0x18000ba88`
- `0x18000dc48`
- `0x18000df50`
- `0x18000df70`
- `0x18000e01c`
- `0x18001558e`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000e151`
- `msvcrt!memcpy_s` at `0x18000e151`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e0d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e0d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e0c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e0c4`

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
0x18000e01c  push    rbx
0x18000e01e  push    rbp
0x18000e01f  push    rsi
0x18000e020  push    rdi
0x18000e021  push    r12
0x18000e023  push    r13
0x18000e025  push    r14
0x18000e027  push    r15
0x18000e029  sub     rsp, 28h
0x18000e02d  mov     [rcx+4], r8d
0x18000e031  lea     rbx, [rcx+20h]
0x18000e035  mov     eax, [rdx+8]
0x18000e038  lea     rsi, [rcx+38h]
0x18000e03c  mov     [rcx+8], eax
0x18000e03f  xor     r12d, r12d
0x18000e042  mov     [rcx+10h], r12
0x18000e046  mov     rbp, rcx
0x18000e049  movzx   eax, word ptr [rdx+40h]
0x18000e04d  mov     r14, rdx
0x18000e050  mov     [rcx+18h], ax
0x18000e054  mov     al, [rdx]
0x18000e056  mov     [rcx+1Ah], al
0x18000e059  mov     [rbx], r12
0x18000e05c  mov     rax, [rdx+88h]
0x18000e063  mov     [rcx+28h], rax
0x18000e067  mov     rax, [rdx+90h]
0x18000e06e  mov     [rcx+30h], rax
0x18000e072  mov     [rsi], r12
0x18000e075  mov     rcx, [rdx+18h]; this
0x18000e079  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000e07e  mov     rcx, [r14+38h]; this
0x18000e082  mov     r15, rax
0x18000e085  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000e08a  mov     rcx, [r14+80h]; this
0x18000e091  add     r15, rax
0x18000e094  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18000e099  add     r15, rax
0x18000e09c  lea     rdi, [rbp+48h]
0x18000e0a0  cmp     [rbp+40h], r12
0x18000e0a4  jz      short loc_18000E0AB
0x18000e0a6  cmp     [rdi], r15
0x18000e0a9  jnb     short loc_18000E0E6
0x18000e0ab  mov     rdx, r15; dwBytes
0x18000e0ae  mov     ecx, 8; dwFlags
0x18000e0b3  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000e0b8  mov     r12, rax
0x18000e0bb  test    rax, rax
0x18000e0be  jz      short loc_18000E0E3
0x18000e0c0  mov     rbx, [rbp+40h]
0x18000e0c4  call    cs:__imp_GetProcessHeap
0x18000e0ca  mov     r8, rbx; lpMem
0x18000e0cd  xor     edx, edx; dwFlags
0x18000e0cf  mov     rcx, rax; hHeap
0x18000e0d2  call    cs:__imp_HeapFree
0x18000e0d8  mov     [rbp+40h], r12
0x18000e0dc  lea     rbx, [rbp+20h]
0x18000e0e0  mov     [rdi], r15
0x18000e0e3  xor     r12d, r12d
0x18000e0e6  mov     rcx, [rbp+40h]; Destination
0x18000e0ea  test    rcx, rcx
0x18000e0ed  jz      loc_18000E17C
0x18000e0f3  mov     rdi, [rdi]
0x18000e0f6  lea     r9, [rbp+10h]
0x18000e0fa  mov     r8, [r14+38h]
0x18000e0fe  add     rdi, rcx
0x18000e101  mov     rdx, rdi
0x18000e104  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000e109  mov     r8, [r14+80h]
0x18000e110  mov     r9, rbx
0x18000e113  mov     rdx, rdi
0x18000e116  mov     rcx, rax; Destination
0x18000e119  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000e11e  mov     rbx, rax
0x18000e121  cmp     rax, rdi
0x18000e124  jz      short loc_18000E164
0x18000e126  mov     rcx, [r14+18h]; this
0x18000e12a  test    rcx, rcx
0x18000e12d  jz      short loc_18000E164
0x18000e12f  cmp     [rcx], r12w
0x18000e133  jz      short loc_18000E164
0x18000e135  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000e13a  mov     rdx, rdi
0x18000e13d  mov     r14, rax
0x18000e140  sub     rdx, rbx; DestinationSize
0x18000e143  cmp     rdx, rax
0x18000e146  jb      short loc_18000E164
0x18000e148  mov     r8, rcx; Source
0x18000e14b  mov     r9, rax; SourceSize
0x18000e14e  mov     rcx, rbx; Destination
0x18000e151  call    cs:__imp_memcpy_s
0x18000e157  test    rsi, rsi
0x18000e15a  jz      short loc_18000E15F
0x18000e15c  mov     [rsi], rbx
0x18000e15f  add     rbx, r14
0x18000e162  jmp     short loc_18000E16C
0x18000e164  test    rsi, rsi
0x18000e167  jz      short loc_18000E16C
0x18000e169  mov     [rsi], r12
0x18000e16c  sub     rdi, rbx
0x18000e16f  xor     edx, edx; Val
0x18000e171  mov     r8, rdi; Size
0x18000e174  mov     rcx, rbx; void *
0x18000e177  call    memset_0
0x18000e17c  add     rsp, 28h
0x18000e180  pop     r15
0x18000e182  pop     r14
0x18000e184  pop     r13
0x18000e186  pop     r12
0x18000e188  pop     rdi
0x18000e189  pop     rsi
0x18000e18a  pop     rbp
0x18000e18b  pop     rbx
0x18000e18c  retn
```

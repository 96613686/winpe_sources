# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180027458`
- end: `0x1800275c9`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `369`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800275d0`

## callees

- `0x180010124`
- `0x180024da8`
- `0x180027410`
- `0x180027430`
- `0x180027458`
- `0x18002fe06`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002758d`
- `msvcrt!memcpy_s` at `0x18002758d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027500`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027500`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002750e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002750e`

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
0x180027458  push    rbx
0x18002745a  push    rbp
0x18002745b  push    rsi
0x18002745c  push    rdi
0x18002745d  push    r12
0x18002745f  push    r13
0x180027461  push    r14
0x180027463  push    r15
0x180027465  sub     rsp, 28h
0x180027469  mov     [rcx+4], r8d
0x18002746d  lea     rbx, [rcx+20h]
0x180027471  mov     eax, [rdx+8]
0x180027474  lea     rsi, [rcx+38h]
0x180027478  mov     [rcx+8], eax
0x18002747b  xor     r12d, r12d
0x18002747e  mov     [rcx+10h], r12
0x180027482  mov     rbp, rcx
0x180027485  movzx   eax, word ptr [rdx+40h]
0x180027489  mov     r14, rdx
0x18002748c  mov     [rcx+18h], ax
0x180027490  mov     al, [rdx]
0x180027492  mov     [rcx+1Ah], al
0x180027495  mov     [rbx], r12
0x180027498  mov     rax, [rdx+88h]
0x18002749f  mov     [rcx+28h], rax
0x1800274a3  mov     rax, [rdx+90h]
0x1800274aa  mov     [rcx+30h], rax
0x1800274ae  mov     [rsi], r12
0x1800274b1  mov     rcx, [rdx+18h]; this
0x1800274b5  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800274ba  mov     rcx, [r14+38h]; this
0x1800274be  mov     r15, rax
0x1800274c1  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800274c6  mov     rcx, [r14+80h]; this
0x1800274cd  add     r15, rax
0x1800274d0  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800274d5  add     r15, rax
0x1800274d8  lea     rdi, [rbp+48h]
0x1800274dc  cmp     [rbp+40h], r12
0x1800274e0  jz      short loc_1800274E7
0x1800274e2  cmp     [rdi], r15
0x1800274e5  jnb     short loc_180027522
0x1800274e7  mov     rdx, r15; dwBytes
0x1800274ea  mov     ecx, 8; dwFlags
0x1800274ef  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800274f4  mov     r12, rax
0x1800274f7  test    rax, rax
0x1800274fa  jz      short loc_18002751F
0x1800274fc  mov     rbx, [rbp+40h]
0x180027500  call    cs:__imp_GetProcessHeap
0x180027506  mov     r8, rbx; lpMem
0x180027509  xor     edx, edx; dwFlags
0x18002750b  mov     rcx, rax; hHeap
0x18002750e  call    cs:__imp_HeapFree
0x180027514  mov     [rbp+40h], r12
0x180027518  lea     rbx, [rbp+20h]
0x18002751c  mov     [rdi], r15
0x18002751f  xor     r12d, r12d
0x180027522  mov     rcx, [rbp+40h]; Destination
0x180027526  test    rcx, rcx
0x180027529  jz      loc_1800275B8
0x18002752f  mov     rdi, [rdi]
0x180027532  lea     r9, [rbp+10h]
0x180027536  mov     r8, [r14+38h]
0x18002753a  add     rdi, rcx
0x18002753d  mov     rdx, rdi
0x180027540  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180027545  mov     r8, [r14+80h]
0x18002754c  mov     r9, rbx
0x18002754f  mov     rdx, rdi
0x180027552  mov     rcx, rax; Destination
0x180027555  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002755a  mov     rbx, rax
0x18002755d  cmp     rax, rdi
0x180027560  jz      short loc_1800275A0
0x180027562  mov     rcx, [r14+18h]; this
0x180027566  test    rcx, rcx
0x180027569  jz      short loc_1800275A0
0x18002756b  cmp     [rcx], r12w
0x18002756f  jz      short loc_1800275A0
0x180027571  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180027576  mov     rdx, rdi
0x180027579  mov     r14, rax
0x18002757c  sub     rdx, rbx; DestinationSize
0x18002757f  cmp     rdx, rax
0x180027582  jb      short loc_1800275A0
0x180027584  mov     r8, rcx; Source
0x180027587  mov     r9, rax; SourceSize
0x18002758a  mov     rcx, rbx; Destination
0x18002758d  call    cs:__imp_memcpy_s
0x180027593  test    rsi, rsi
0x180027596  jz      short loc_18002759B
0x180027598  mov     [rsi], rbx
0x18002759b  add     rbx, r14
0x18002759e  jmp     short loc_1800275A8
0x1800275a0  test    rsi, rsi
0x1800275a3  jz      short loc_1800275A8
0x1800275a5  mov     [rsi], r12
0x1800275a8  sub     rdi, rbx
0x1800275ab  xor     edx, edx; Val
0x1800275ad  mov     r8, rdi; Size
0x1800275b0  mov     rcx, rbx; void *
0x1800275b3  call    memset_0
0x1800275b8  add     rsp, 28h
0x1800275bc  pop     r15
0x1800275be  pop     r14
0x1800275c0  pop     r13
0x1800275c2  pop     r12
0x1800275c4  pop     rdi
0x1800275c5  pop     rsi
0x1800275c6  pop     rbp
0x1800275c7  pop     rbx
0x1800275c8  retn
```

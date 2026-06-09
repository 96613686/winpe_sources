# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180028f04`
- end: `0x180029088`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `388`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180029090`

## callees

- `0x180010de8`
- `0x180026738`
- `0x180028eb4`
- `0x180028ed8`
- `0x180028f04`
- `0x180032be6`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180029045`
- `msvcrt!memcpy_s` at `0x180029045`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028fac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028fac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028fc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028fc0`

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
0x180028f04  push    rbx
0x180028f06  push    rbp
0x180028f07  push    rsi
0x180028f08  push    rdi
0x180028f09  push    r12
0x180028f0b  push    r13
0x180028f0d  push    r14
0x180028f0f  push    r15
0x180028f11  sub     rsp, 28h
0x180028f15  mov     [rcx+4], r8d
0x180028f19  lea     rbx, [rcx+20h]
0x180028f1d  mov     eax, [rdx+8]
0x180028f20  lea     rsi, [rcx+38h]
0x180028f24  mov     [rcx+8], eax
0x180028f27  xor     r12d, r12d
0x180028f2a  mov     [rcx+10h], r12
0x180028f2e  mov     rbp, rcx
0x180028f31  movzx   eax, word ptr [rdx+40h]
0x180028f35  mov     r14, rdx
0x180028f38  mov     [rcx+18h], ax
0x180028f3c  mov     al, [rdx]
0x180028f3e  mov     [rcx+1Ah], al
0x180028f41  mov     [rbx], r12
0x180028f44  mov     rax, [rdx+88h]
0x180028f4b  mov     [rcx+28h], rax
0x180028f4f  mov     rax, [rdx+90h]
0x180028f56  mov     [rcx+30h], rax
0x180028f5a  mov     [rsi], r12
0x180028f5d  mov     rcx, [rdx+18h]; this
0x180028f61  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180028f66  mov     rcx, [r14+38h]; this
0x180028f6a  mov     r15, rax
0x180028f6d  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180028f72  mov     rcx, [r14+80h]; this
0x180028f79  add     r15, rax
0x180028f7c  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180028f81  add     r15, rax
0x180028f84  lea     rdi, [rbp+48h]
0x180028f88  cmp     [rbp+40h], r12
0x180028f8c  jz      short loc_180028F93
0x180028f8e  cmp     [rdi], r15
0x180028f91  jnb     short loc_180028FDA
0x180028f93  mov     rdx, r15; dwBytes
0x180028f96  mov     ecx, 8; dwFlags
0x180028f9b  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180028fa0  mov     r12, rax
0x180028fa3  test    rax, rax
0x180028fa6  jz      short loc_180028FD7
0x180028fa8  mov     rbx, [rbp+40h]
0x180028fac  call    cs:__imp_GetProcessHeap
0x180028fb3  nop     dword ptr [rax+rax+00h]
0x180028fb8  mov     r8, rbx; lpMem
0x180028fbb  xor     edx, edx; dwFlags
0x180028fbd  mov     rcx, rax; hHeap
0x180028fc0  call    cs:__imp_HeapFree
0x180028fc7  nop     dword ptr [rax+rax+00h]
0x180028fcc  mov     [rbp+40h], r12
0x180028fd0  lea     rbx, [rbp+20h]
0x180028fd4  mov     [rdi], r15
0x180028fd7  xor     r12d, r12d
0x180028fda  mov     rcx, [rbp+40h]; Destination
0x180028fde  test    rcx, rcx
0x180028fe1  jz      loc_180029076
0x180028fe7  mov     rdi, [rdi]
0x180028fea  lea     r9, [rbp+10h]
0x180028fee  mov     r8, [r14+38h]
0x180028ff2  add     rdi, rcx
0x180028ff5  mov     rdx, rdi
0x180028ff8  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180028ffd  mov     r8, [r14+80h]
0x180029004  mov     r9, rbx
0x180029007  mov     rdx, rdi
0x18002900a  mov     rcx, rax; Destination
0x18002900d  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180029012  mov     rbx, rax
0x180029015  cmp     rax, rdi
0x180029018  jz      short loc_18002905E
0x18002901a  mov     rcx, [r14+18h]; this
0x18002901e  test    rcx, rcx
0x180029021  jz      short loc_18002905E
0x180029023  cmp     [rcx], r12w
0x180029027  jz      short loc_18002905E
0x180029029  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18002902e  mov     rdx, rdi
0x180029031  mov     r14, rax
0x180029034  sub     rdx, rbx; DestinationSize
0x180029037  cmp     rdx, rax
0x18002903a  jb      short loc_18002905E
0x18002903c  mov     r8, rcx; Source
0x18002903f  mov     r9, rax; SourceSize
0x180029042  mov     rcx, rbx; Destination
0x180029045  call    cs:__imp_memcpy_s
0x18002904c  nop     dword ptr [rax+rax+00h]
0x180029051  test    rsi, rsi
0x180029054  jz      short loc_180029059
0x180029056  mov     [rsi], rbx
0x180029059  add     rbx, r14
0x18002905c  jmp     short loc_180029066
0x18002905e  test    rsi, rsi
0x180029061  jz      short loc_180029066
0x180029063  mov     [rsi], r12
0x180029066  sub     rdi, rbx
0x180029069  xor     edx, edx; Val
0x18002906b  mov     r8, rdi; Size
0x18002906e  mov     rcx, rbx; void *
0x180029071  call    memset_0
0x180029076  add     rsp, 28h
0x18002907a  pop     r15
0x18002907c  pop     r14
0x18002907e  pop     r13
0x180029080  pop     r12
0x180029082  pop     rdi
0x180029083  pop     rsi
0x180029084  pop     rbp
0x180029085  pop     rbx
0x180029086  retn
```

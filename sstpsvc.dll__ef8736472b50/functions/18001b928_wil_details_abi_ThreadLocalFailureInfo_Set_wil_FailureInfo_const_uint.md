# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18001b928`
- end: `0x18001ba6b`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001bb64`

## callees

- `0x180018234`
- `0x1800182b4`
- `0x18001aa40`
- `0x18001b7a4`
- `0x18001b7c8`
- `0x18001b928`
- `0x18001d1da`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b9eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b9eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b9d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b9d7`

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
0x18001b928  push    rbx
0x18001b92a  push    rbp
0x18001b92b  push    rsi
0x18001b92c  push    rdi
0x18001b92d  push    r12
0x18001b92f  push    r13
0x18001b931  push    r14
0x18001b933  push    r15
0x18001b935  sub     rsp, 28h
0x18001b939  mov     [rcx+4], r8d
0x18001b93d  lea     r14, [rcx+38h]
0x18001b941  mov     eax, [rdx+8]
0x18001b944  mov     rsi, rcx
0x18001b947  mov     [rcx+8], eax
0x18001b94a  mov     r15, rdx
0x18001b94d  mov     qword ptr [rcx+10h], 0
0x18001b955  movzx   eax, word ptr [rdx+40h]
0x18001b959  mov     [rcx+18h], ax
0x18001b95d  mov     al, [rdx]
0x18001b95f  mov     [rcx+1Ah], al
0x18001b962  mov     qword ptr [rcx+20h], 0
0x18001b96a  mov     rax, [rdx+88h]
0x18001b971  mov     [rcx+28h], rax
0x18001b975  mov     rax, [rdx+90h]
0x18001b97c  mov     [rcx+30h], rax
0x18001b980  mov     qword ptr [r14], 0
0x18001b987  mov     rcx, [rdx+18h]; this
0x18001b98b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001b990  mov     rcx, [r15+38h]; this
0x18001b994  mov     rbp, rax
0x18001b997  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001b99c  mov     rcx, [r15+80h]; this
0x18001b9a3  add     rbp, rax
0x18001b9a6  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001b9ab  add     rbp, rax
0x18001b9ae  lea     rdi, [rsi+48h]
0x18001b9b2  cmp     qword ptr [rsi+40h], 0
0x18001b9b7  jz      short loc_18001B9BE
0x18001b9b9  cmp     [rdi], rbp
0x18001b9bc  jnb     short loc_18001BA02
0x18001b9be  mov     rdx, rbp; dwBytes
0x18001b9c1  mov     ecx, 8; dwFlags
0x18001b9c6  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001b9cb  mov     r14, rax
0x18001b9ce  test    rax, rax
0x18001b9d1  jz      short loc_18001B9FE
0x18001b9d3  mov     rbx, [rsi+40h]
0x18001b9d7  call    cs:__imp_GetProcessHeap
0x18001b9de  nop     dword ptr [rax+rax+00h]
0x18001b9e3  mov     r8, rbx; lpMem
0x18001b9e6  xor     edx, edx; dwFlags
0x18001b9e8  mov     rcx, rax; hHeap
0x18001b9eb  call    cs:__imp_HeapFree
0x18001b9f2  nop     dword ptr [rax+rax+00h]
0x18001b9f7  mov     [rsi+40h], r14
0x18001b9fb  mov     [rdi], rbp
0x18001b9fe  lea     r14, [rsi+38h]
0x18001ba02  mov     rcx, [rsi+40h]; Destination
0x18001ba06  test    rcx, rcx
0x18001ba09  jz      short loc_18001BA59
0x18001ba0b  mov     rbx, [rdi]
0x18001ba0e  lea     r9, [rsi+10h]
0x18001ba12  mov     r8, [r15+38h]
0x18001ba16  add     rbx, rcx
0x18001ba19  mov     rdx, rbx
0x18001ba1c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001ba21  mov     r8, [r15+80h]
0x18001ba28  lea     r9, [rsi+20h]
0x18001ba2c  mov     rdx, rbx
0x18001ba2f  mov     rcx, rax; Destination
0x18001ba32  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001ba37  mov     r8, [r15+18h]
0x18001ba3b  mov     r9, r14
0x18001ba3e  mov     rdx, rbx
0x18001ba41  mov     rcx, rax; Destination
0x18001ba44  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18001ba49  sub     rbx, rax
0x18001ba4c  xor     edx, edx; Val
0x18001ba4e  mov     r8, rbx; Size
0x18001ba51  mov     rcx, rax; void *
0x18001ba54  call    memset_0
0x18001ba59  add     rsp, 28h
0x18001ba5d  pop     r15
0x18001ba5f  pop     r14
0x18001ba61  pop     r13
0x18001ba63  pop     r12
0x18001ba65  pop     rdi
0x18001ba66  pop     rsi
0x18001ba67  pop     rbp
0x18001ba68  pop     rbx
0x18001ba69  retn
```

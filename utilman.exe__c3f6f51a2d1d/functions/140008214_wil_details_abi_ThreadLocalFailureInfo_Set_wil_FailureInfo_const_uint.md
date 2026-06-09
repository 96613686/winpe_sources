# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x140008214`
- end: `0x140008357`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1400086b4`

## callees

- `0x140002fa0`
- `0x1400040e0`
- `0x140004158`
- `0x140007100`
- `0x14000806c`
- `0x140008090`
- `0x140008214`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400082d7`
- `KERNEL32!HeapFree` at `0x1400082d7`
- `KERNEL32!GetProcessHeap` at `0x1400082c3`
- `KERNEL32!GetProcessHeap` at `0x1400082c3`

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
0x140008214  push    rbx
0x140008216  push    rbp
0x140008217  push    rsi
0x140008218  push    rdi
0x140008219  push    r12
0x14000821b  push    r13
0x14000821d  push    r14
0x14000821f  push    r15
0x140008221  sub     rsp, 28h
0x140008225  mov     [rcx+4], r8d
0x140008229  lea     r14, [rcx+38h]
0x14000822d  mov     eax, [rdx+8]
0x140008230  mov     rsi, rcx
0x140008233  mov     [rcx+8], eax
0x140008236  mov     r15, rdx
0x140008239  mov     qword ptr [rcx+10h], 0
0x140008241  movzx   eax, word ptr [rdx+40h]
0x140008245  mov     [rcx+18h], ax
0x140008249  mov     al, [rdx]
0x14000824b  mov     [rcx+1Ah], al
0x14000824e  mov     qword ptr [rcx+20h], 0
0x140008256  mov     rax, [rdx+88h]
0x14000825d  mov     [rcx+28h], rax
0x140008261  mov     rax, [rdx+90h]
0x140008268  mov     [rcx+30h], rax
0x14000826c  mov     qword ptr [r14], 0
0x140008273  mov     rcx, [rdx+18h]; this
0x140008277  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x14000827c  mov     rcx, [r15+38h]; this
0x140008280  mov     rbp, rax
0x140008283  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140008288  mov     rcx, [r15+80h]; this
0x14000828f  add     rbp, rax
0x140008292  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x140008297  add     rbp, rax
0x14000829a  lea     rdi, [rsi+48h]
0x14000829e  cmp     qword ptr [rsi+40h], 0
0x1400082a3  jz      short loc_1400082AA
0x1400082a5  cmp     [rdi], rbp
0x1400082a8  jnb     short loc_1400082EE
0x1400082aa  mov     rdx, rbp; dwBytes
0x1400082ad  mov     ecx, 8; dwFlags
0x1400082b2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1400082b7  mov     r14, rax
0x1400082ba  test    rax, rax
0x1400082bd  jz      short loc_1400082EA
0x1400082bf  mov     rbx, [rsi+40h]
0x1400082c3  call    cs:__imp_GetProcessHeap
0x1400082ca  nop     dword ptr [rax+rax+00h]
0x1400082cf  mov     r8, rbx; lpMem
0x1400082d2  xor     edx, edx; dwFlags
0x1400082d4  mov     rcx, rax; hHeap
0x1400082d7  call    cs:__imp_HeapFree
0x1400082de  nop     dword ptr [rax+rax+00h]
0x1400082e3  mov     [rsi+40h], r14
0x1400082e7  mov     [rdi], rbp
0x1400082ea  lea     r14, [rsi+38h]
0x1400082ee  mov     rcx, [rsi+40h]; Destination
0x1400082f2  test    rcx, rcx
0x1400082f5  jz      short loc_140008345
0x1400082f7  mov     rbx, [rdi]
0x1400082fa  lea     r9, [rsi+10h]
0x1400082fe  mov     r8, [r15+38h]
0x140008302  add     rbx, rcx
0x140008305  mov     rdx, rbx
0x140008308  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000830d  mov     r8, [r15+80h]
0x140008314  lea     r9, [rsi+20h]
0x140008318  mov     rdx, rbx
0x14000831b  mov     rcx, rax; Destination
0x14000831e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140008323  mov     r8, [r15+18h]
0x140008327  mov     r9, r14
0x14000832a  mov     rdx, rbx
0x14000832d  mov     rcx, rax; Destination
0x140008330  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x140008335  sub     rbx, rax
0x140008338  xor     edx, edx; Val
0x14000833a  mov     r8, rbx; Size
0x14000833d  mov     rcx, rax; void *
0x140008340  call    memset_0
0x140008345  add     rsp, 28h
0x140008349  pop     r15
0x14000834b  pop     r14
0x14000834d  pop     r13
0x14000834f  pop     r12
0x140008351  pop     rdi
0x140008352  pop     rsi
0x140008353  pop     rbp
0x140008354  pop     rbx
0x140008355  retn
```

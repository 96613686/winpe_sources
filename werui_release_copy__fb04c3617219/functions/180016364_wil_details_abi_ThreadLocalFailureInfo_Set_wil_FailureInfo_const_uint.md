# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180016364`
- end: `0x18001649a`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800164a0`

## callees

- `0x1800049e4`
- `0x180004a5c`
- `0x180005414`
- `0x180005434`
- `0x180016128`
- `0x180016364`
- `0x180016c1e`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180016413`
- `KERNEL32!GetProcessHeap` at `0x180016413`
- `KERNEL32!HeapFree` at `0x180016421`
- `KERNEL32!HeapFree` at `0x180016421`

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
0x180016364  push    rbx
0x180016366  push    rbp
0x180016367  push    rsi
0x180016368  push    rdi
0x180016369  push    r12
0x18001636b  push    r13
0x18001636d  push    r14
0x18001636f  push    r15
0x180016371  sub     rsp, 28h
0x180016375  mov     [rcx+4], r8d
0x180016379  lea     r14, [rcx+38h]
0x18001637d  mov     eax, [rdx+8]
0x180016380  mov     rsi, rcx
0x180016383  mov     [rcx+8], eax
0x180016386  mov     r15, rdx
0x180016389  mov     qword ptr [rcx+10h], 0
0x180016391  movzx   eax, word ptr [rdx+40h]
0x180016395  mov     [rcx+18h], ax
0x180016399  mov     al, [rdx]
0x18001639b  mov     [rcx+1Ah], al
0x18001639e  mov     qword ptr [rcx+20h], 0
0x1800163a6  mov     rax, [rdx+88h]
0x1800163ad  mov     [rcx+28h], rax
0x1800163b1  mov     rax, [rdx+90h]
0x1800163b8  mov     [rcx+30h], rax
0x1800163bc  mov     qword ptr [r14], 0
0x1800163c3  mov     rcx, [rdx+18h]; this
0x1800163c7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800163cc  mov     rcx, [r15+38h]; this
0x1800163d0  mov     rbp, rax
0x1800163d3  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800163d8  mov     rcx, [r15+80h]; this
0x1800163df  add     rbp, rax
0x1800163e2  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800163e7  add     rbp, rax
0x1800163ea  lea     rdi, [rsi+48h]
0x1800163ee  cmp     qword ptr [rsi+40h], 0
0x1800163f3  jz      short loc_1800163FA
0x1800163f5  cmp     [rdi], rbp
0x1800163f8  jnb     short loc_180016432
0x1800163fa  mov     rdx, rbp; dwBytes
0x1800163fd  mov     ecx, 8; dwFlags
0x180016402  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180016407  mov     r14, rax
0x18001640a  test    rax, rax
0x18001640d  jz      short loc_18001642E
0x18001640f  mov     rbx, [rsi+40h]
0x180016413  call    cs:__imp_GetProcessHeap
0x180016419  mov     r8, rbx; lpMem
0x18001641c  xor     edx, edx; dwFlags
0x18001641e  mov     rcx, rax; hHeap
0x180016421  call    cs:__imp_HeapFree
0x180016427  mov     [rsi+40h], r14
0x18001642b  mov     [rdi], rbp
0x18001642e  lea     r14, [rsi+38h]
0x180016432  mov     rcx, [rsi+40h]; Destination
0x180016436  test    rcx, rcx
0x180016439  jz      short loc_180016489
0x18001643b  mov     rbx, [rdi]
0x18001643e  lea     r9, [rsi+10h]
0x180016442  mov     r8, [r15+38h]
0x180016446  add     rbx, rcx
0x180016449  mov     rdx, rbx
0x18001644c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180016451  mov     r8, [r15+80h]
0x180016458  lea     r9, [rsi+20h]
0x18001645c  mov     rdx, rbx
0x18001645f  mov     rcx, rax; Destination
0x180016462  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180016467  mov     r8, [r15+18h]
0x18001646b  mov     r9, r14
0x18001646e  mov     rdx, rbx
0x180016471  mov     rcx, rax; Destination
0x180016474  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180016479  sub     rbx, rax
0x18001647c  xor     edx, edx; Val
0x18001647e  mov     r8, rbx; Size
0x180016481  mov     rcx, rax; void *
0x180016484  call    memset_0
0x180016489  add     rsp, 28h
0x18001648d  pop     r15
0x18001648f  pop     r14
0x180016491  pop     r13
0x180016493  pop     r12
0x180016495  pop     rdi
0x180016496  pop     rsi
0x180016497  pop     rbp
0x180016498  pop     rbx
0x180016499  retn
```

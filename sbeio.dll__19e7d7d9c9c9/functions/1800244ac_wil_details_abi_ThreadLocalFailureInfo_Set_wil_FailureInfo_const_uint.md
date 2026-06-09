# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800244ac`
- end: `0x1800245e2`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180024cbc`

## callees

- `0x180001f1c`
- `0x180014d00`
- `0x180014d78`
- `0x18001f77c`
- `0x1800243e4`
- `0x180024404`
- `0x1800244ac`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180024569`
- `KERNEL32!HeapFree` at `0x180024569`
- `KERNEL32!GetProcessHeap` at `0x18002455b`
- `KERNEL32!GetProcessHeap` at `0x18002455b`

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
0x1800244ac  push    rbx
0x1800244ae  push    rbp
0x1800244af  push    rsi
0x1800244b0  push    rdi
0x1800244b1  push    r12
0x1800244b3  push    r13
0x1800244b5  push    r14
0x1800244b7  push    r15
0x1800244b9  sub     rsp, 28h
0x1800244bd  mov     [rcx+4], r8d
0x1800244c1  lea     r14, [rcx+38h]
0x1800244c5  mov     eax, [rdx+8]
0x1800244c8  mov     rsi, rcx
0x1800244cb  mov     [rcx+8], eax
0x1800244ce  mov     r15, rdx
0x1800244d1  mov     qword ptr [rcx+10h], 0
0x1800244d9  movzx   eax, word ptr [rdx+40h]
0x1800244dd  mov     [rcx+18h], ax
0x1800244e1  mov     al, [rdx]
0x1800244e3  mov     [rcx+1Ah], al
0x1800244e6  mov     qword ptr [rcx+20h], 0
0x1800244ee  mov     rax, [rdx+88h]
0x1800244f5  mov     [rcx+28h], rax
0x1800244f9  mov     rax, [rdx+90h]
0x180024500  mov     [rcx+30h], rax
0x180024504  mov     qword ptr [r14], 0
0x18002450b  mov     rcx, [rdx+18h]; this
0x18002450f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180024514  mov     rcx, [r15+38h]; this
0x180024518  mov     rbp, rax
0x18002451b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180024520  mov     rcx, [r15+80h]; this
0x180024527  add     rbp, rax
0x18002452a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18002452f  add     rbp, rax
0x180024532  lea     rdi, [rsi+48h]
0x180024536  cmp     qword ptr [rsi+40h], 0
0x18002453b  jz      short loc_180024542
0x18002453d  cmp     [rdi], rbp
0x180024540  jnb     short loc_18002457A
0x180024542  mov     rdx, rbp; dwBytes
0x180024545  mov     ecx, 8; dwFlags
0x18002454a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002454f  mov     r14, rax
0x180024552  test    rax, rax
0x180024555  jz      short loc_180024576
0x180024557  mov     rbx, [rsi+40h]
0x18002455b  call    cs:__imp_GetProcessHeap
0x180024561  mov     r8, rbx; lpMem
0x180024564  xor     edx, edx; dwFlags
0x180024566  mov     rcx, rax; hHeap
0x180024569  call    cs:__imp_HeapFree
0x18002456f  mov     [rsi+40h], r14
0x180024573  mov     [rdi], rbp
0x180024576  lea     r14, [rsi+38h]
0x18002457a  mov     rcx, [rsi+40h]; Destination
0x18002457e  test    rcx, rcx
0x180024581  jz      short loc_1800245D1
0x180024583  mov     rbx, [rdi]
0x180024586  lea     r9, [rsi+10h]
0x18002458a  mov     r8, [r15+38h]
0x18002458e  add     rbx, rcx
0x180024591  mov     rdx, rbx
0x180024594  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180024599  mov     r8, [r15+80h]
0x1800245a0  lea     r9, [rsi+20h]
0x1800245a4  mov     rdx, rbx
0x1800245a7  mov     rcx, rax; Destination
0x1800245aa  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800245af  mov     r8, [r15+18h]
0x1800245b3  mov     r9, r14
0x1800245b6  mov     rdx, rbx
0x1800245b9  mov     rcx, rax; Destination
0x1800245bc  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800245c1  sub     rbx, rax
0x1800245c4  xor     edx, edx; Val
0x1800245c6  mov     r8, rbx; Size
0x1800245c9  mov     rcx, rax; void *
0x1800245cc  call    memset_0
0x1800245d1  add     rsp, 28h
0x1800245d5  pop     r15
0x1800245d7  pop     r14
0x1800245d9  pop     r13
0x1800245db  pop     r12
0x1800245dd  pop     rdi
0x1800245de  pop     rsi
0x1800245df  pop     rbp
0x1800245e0  pop     rbx
0x1800245e1  retn
```

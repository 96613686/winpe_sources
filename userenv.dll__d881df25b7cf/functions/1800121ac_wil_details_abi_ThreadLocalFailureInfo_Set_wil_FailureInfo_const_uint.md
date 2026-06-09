# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1800121ac`
- end: `0x1800122ef`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800122f8`

## callees

- `0x180006668`
- `0x18000efe0`
- `0x18000fd00`
- `0x18000fd78`
- `0x180010544`
- `0x180010568`
- `0x1800121ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001226f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001226f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001225b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001225b`

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
0x1800121ac  push    rbx
0x1800121ae  push    rbp
0x1800121af  push    rsi
0x1800121b0  push    rdi
0x1800121b1  push    r12
0x1800121b3  push    r13
0x1800121b5  push    r14
0x1800121b7  push    r15
0x1800121b9  sub     rsp, 28h
0x1800121bd  mov     [rcx+4], r8d
0x1800121c1  lea     r14, [rcx+38h]
0x1800121c5  mov     eax, [rdx+8]
0x1800121c8  mov     rsi, rcx
0x1800121cb  mov     [rcx+8], eax
0x1800121ce  mov     r15, rdx
0x1800121d1  mov     qword ptr [rcx+10h], 0
0x1800121d9  movzx   eax, word ptr [rdx+40h]
0x1800121dd  mov     [rcx+18h], ax
0x1800121e1  mov     al, [rdx]
0x1800121e3  mov     [rcx+1Ah], al
0x1800121e6  mov     qword ptr [rcx+20h], 0
0x1800121ee  mov     rax, [rdx+88h]
0x1800121f5  mov     [rcx+28h], rax
0x1800121f9  mov     rax, [rdx+90h]
0x180012200  mov     [rcx+30h], rax
0x180012204  mov     qword ptr [r14], 0
0x18001220b  mov     rcx, [rdx+18h]; this
0x18001220f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180012214  mov     rcx, [r15+38h]; this
0x180012218  mov     rbp, rax
0x18001221b  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x180012220  mov     rcx, [r15+80h]; this
0x180012227  add     rbp, rax
0x18001222a  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001222f  add     rbp, rax
0x180012232  lea     rdi, [rsi+48h]
0x180012236  cmp     qword ptr [rsi+40h], 0
0x18001223b  jz      short loc_180012242
0x18001223d  cmp     [rdi], rbp
0x180012240  jnb     short loc_180012286
0x180012242  mov     rdx, rbp; dwBytes
0x180012245  mov     ecx, 8; dwFlags
0x18001224a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001224f  mov     r14, rax
0x180012252  test    rax, rax
0x180012255  jz      short loc_180012282
0x180012257  mov     rbx, [rsi+40h]
0x18001225b  call    cs:__imp_GetProcessHeap
0x180012262  nop     dword ptr [rax+rax+00h]
0x180012267  mov     r8, rbx; lpMem
0x18001226a  xor     edx, edx; dwFlags
0x18001226c  mov     rcx, rax; hHeap
0x18001226f  call    cs:__imp_HeapFree
0x180012276  nop     dword ptr [rax+rax+00h]
0x18001227b  mov     [rsi+40h], r14
0x18001227f  mov     [rdi], rbp
0x180012282  lea     r14, [rsi+38h]
0x180012286  mov     rcx, [rsi+40h]; Destination
0x18001228a  test    rcx, rcx
0x18001228d  jz      short loc_1800122DD
0x18001228f  mov     rbx, [rdi]
0x180012292  lea     r9, [rsi+10h]
0x180012296  mov     r8, [r15+38h]
0x18001229a  add     rbx, rcx
0x18001229d  mov     rdx, rbx
0x1800122a0  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800122a5  mov     r8, [r15+80h]
0x1800122ac  lea     r9, [rsi+20h]
0x1800122b0  mov     rdx, rbx
0x1800122b3  mov     rcx, rax; Destination
0x1800122b6  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800122bb  mov     r8, [r15+18h]
0x1800122bf  mov     r9, r14
0x1800122c2  mov     rdx, rbx
0x1800122c5  mov     rcx, rax; Destination
0x1800122c8  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800122cd  sub     rbx, rax
0x1800122d0  xor     edx, edx; Val
0x1800122d2  mov     r8, rbx; Size
0x1800122d5  mov     rcx, rax; void *
0x1800122d8  call    memset_0
0x1800122dd  add     rsp, 28h
0x1800122e1  pop     r15
0x1800122e3  pop     r14
0x1800122e5  pop     r13
0x1800122e7  pop     r12
0x1800122e9  pop     rdi
0x1800122ea  pop     rsi
0x1800122eb  pop     rbp
0x1800122ec  pop     rbx
0x1800122ed  retn
```

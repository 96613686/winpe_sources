# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180022550`
- end: `0x180022686`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800228e8`

## callees

- `0x18001776c`
- `0x180020d34`
- `0x18002159c`
- `0x180021614`
- `0x18002214c`
- `0x180022488`
- `0x180022550`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002260d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002260d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800225ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800225ff`

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
0x180022550  push    rbx
0x180022552  push    rbp
0x180022553  push    rsi
0x180022554  push    rdi
0x180022555  push    r12
0x180022557  push    r13
0x180022559  push    r14
0x18002255b  push    r15
0x18002255d  sub     rsp, 28h
0x180022561  mov     [rcx+4], r8d
0x180022565  lea     r14, [rcx+38h]
0x180022569  mov     eax, [rdx+8]
0x18002256c  mov     rsi, rcx
0x18002256f  mov     [rcx+8], eax
0x180022572  mov     r15, rdx
0x180022575  mov     qword ptr [rcx+10h], 0
0x18002257d  movzx   eax, word ptr [rdx+40h]
0x180022581  mov     [rcx+18h], ax
0x180022585  mov     al, [rdx]
0x180022587  mov     [rcx+1Ah], al
0x18002258a  mov     qword ptr [rcx+20h], 0
0x180022592  mov     rax, [rdx+88h]
0x180022599  mov     [rcx+28h], rax
0x18002259d  mov     rax, [rdx+90h]
0x1800225a4  mov     [rcx+30h], rax
0x1800225a8  mov     qword ptr [r14], 0
0x1800225af  mov     rcx, [rdx+18h]; this
0x1800225b3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800225b8  mov     rcx, [r15+38h]; this
0x1800225bc  mov     rbp, rax
0x1800225bf  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800225c4  mov     rcx, [r15+80h]; this
0x1800225cb  add     rbp, rax
0x1800225ce  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800225d3  add     rbp, rax
0x1800225d6  lea     rdi, [rsi+48h]
0x1800225da  cmp     qword ptr [rsi+40h], 0
0x1800225df  jz      short loc_1800225E6
0x1800225e1  cmp     [rdi], rbp
0x1800225e4  jnb     short loc_18002261E
0x1800225e6  mov     rdx, rbp; dwBytes
0x1800225e9  mov     ecx, 8; dwFlags
0x1800225ee  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800225f3  mov     r14, rax
0x1800225f6  test    rax, rax
0x1800225f9  jz      short loc_18002261A
0x1800225fb  mov     rbx, [rsi+40h]
0x1800225ff  call    cs:__imp_GetProcessHeap
0x180022605  mov     r8, rbx; lpMem
0x180022608  xor     edx, edx; dwFlags
0x18002260a  mov     rcx, rax; hHeap
0x18002260d  call    cs:__imp_HeapFree
0x180022613  mov     [rsi+40h], r14
0x180022617  mov     [rdi], rbp
0x18002261a  lea     r14, [rsi+38h]
0x18002261e  mov     rcx, [rsi+40h]; Destination
0x180022622  test    rcx, rcx
0x180022625  jz      short loc_180022675
0x180022627  mov     rbx, [rdi]
0x18002262a  lea     r9, [rsi+10h]
0x18002262e  mov     r8, [r15+38h]
0x180022632  add     rbx, rcx
0x180022635  mov     rdx, rbx
0x180022638  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18002263d  mov     r8, [r15+80h]
0x180022644  lea     r9, [rsi+20h]
0x180022648  mov     rdx, rbx
0x18002264b  mov     rcx, rax; Destination
0x18002264e  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180022653  mov     r8, [r15+18h]
0x180022657  mov     r9, r14
0x18002265a  mov     rdx, rbx
0x18002265d  mov     rcx, rax; Destination
0x180022660  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x180022665  sub     rbx, rax
0x180022668  xor     edx, edx; Val
0x18002266a  mov     r8, rbx; Size
0x18002266d  mov     rcx, rax; void *
0x180022670  call    memset_0
0x180022675  add     rsp, 28h
0x180022679  pop     r15
0x18002267b  pop     r14
0x18002267d  pop     r13
0x18002267f  pop     r12
0x180022681  pop     rdi
0x180022682  pop     rsi
0x180022683  pop     rbp
0x180022684  pop     rbx
0x180022685  retn
```

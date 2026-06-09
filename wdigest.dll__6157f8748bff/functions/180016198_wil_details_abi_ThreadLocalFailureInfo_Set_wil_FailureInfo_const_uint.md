# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180016198`
- end: `0x1800162ce`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `310`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800162d4`

## callees

- `0x180013304`
- `0x1800141b0`
- `0x180014228`
- `0x180015c30`
- `0x180016058`
- `0x180016078`
- `0x180016198`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016255`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016255`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016247`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016247`

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
0x180016198  push    rbx
0x18001619a  push    rbp
0x18001619b  push    rsi
0x18001619c  push    rdi
0x18001619d  push    r12
0x18001619f  push    r13
0x1800161a1  push    r14
0x1800161a3  push    r15
0x1800161a5  sub     rsp, 28h
0x1800161a9  mov     [rcx+4], r8d
0x1800161ad  lea     r14, [rcx+38h]
0x1800161b1  mov     eax, [rdx+8]
0x1800161b4  mov     rsi, rcx
0x1800161b7  mov     [rcx+8], eax
0x1800161ba  mov     r15, rdx
0x1800161bd  mov     qword ptr [rcx+10h], 0
0x1800161c5  movzx   eax, word ptr [rdx+40h]
0x1800161c9  mov     [rcx+18h], ax
0x1800161cd  mov     al, [rdx]
0x1800161cf  mov     [rcx+1Ah], al
0x1800161d2  mov     qword ptr [rcx+20h], 0
0x1800161da  mov     rax, [rdx+88h]
0x1800161e1  mov     [rcx+28h], rax
0x1800161e5  mov     rax, [rdx+90h]
0x1800161ec  mov     [rcx+30h], rax
0x1800161f0  mov     qword ptr [r14], 0
0x1800161f7  mov     rcx, [rdx+18h]; this
0x1800161fb  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180016200  mov     rcx, [r15+38h]; this
0x180016204  mov     rbp, rax
0x180016207  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001620c  mov     rcx, [r15+80h]; this
0x180016213  add     rbp, rax
0x180016216  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x18001621b  add     rbp, rax
0x18001621e  lea     rdi, [rsi+48h]
0x180016222  cmp     qword ptr [rsi+40h], 0
0x180016227  jz      short loc_18001622E
0x180016229  cmp     [rdi], rbp
0x18001622c  jnb     short loc_180016266
0x18001622e  mov     rdx, rbp; dwBytes
0x180016231  mov     ecx, 8; dwFlags
0x180016236  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18001623b  mov     r14, rax
0x18001623e  test    rax, rax
0x180016241  jz      short loc_180016262
0x180016243  mov     rbx, [rsi+40h]
0x180016247  call    cs:__imp_GetProcessHeap
0x18001624d  mov     r8, rbx; lpMem
0x180016250  xor     edx, edx; dwFlags
0x180016252  mov     rcx, rax; hHeap
0x180016255  call    cs:__imp_HeapFree
0x18001625b  mov     [rsi+40h], r14
0x18001625f  mov     [rdi], rbp
0x180016262  lea     r14, [rsi+38h]
0x180016266  mov     rcx, [rsi+40h]; Destination
0x18001626a  test    rcx, rcx
0x18001626d  jz      short loc_1800162BD
0x18001626f  mov     rbx, [rdi]
0x180016272  lea     r9, [rsi+10h]
0x180016276  mov     r8, [r15+38h]
0x18001627a  add     rbx, rcx
0x18001627d  mov     rdx, rbx
0x180016280  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180016285  mov     r8, [r15+80h]
0x18001628c  lea     r9, [rsi+20h]
0x180016290  mov     rdx, rbx
0x180016293  mov     rcx, rax; Destination
0x180016296  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18001629b  mov     r8, [r15+18h]
0x18001629f  mov     r9, r14
0x1800162a2  mov     rdx, rbx
0x1800162a5  mov     rcx, rax; Destination
0x1800162a8  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x1800162ad  sub     rbx, rax
0x1800162b0  xor     edx, edx; Val
0x1800162b2  mov     r8, rbx; Size
0x1800162b5  mov     rcx, rax; void *
0x1800162b8  call    memset_0
0x1800162bd  add     rsp, 28h
0x1800162c1  pop     r15
0x1800162c3  pop     r14
0x1800162c5  pop     r13
0x1800162c7  pop     r12
0x1800162c9  pop     rdi
0x1800162ca  pop     rsi
0x1800162cb  pop     rbp
0x1800162cc  pop     rbx
0x1800162cd  retn
```

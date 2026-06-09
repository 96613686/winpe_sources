# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x18000926c`
- end: `0x1800093af`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `323`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180009620`

## callees

- `0x18000734c`
- `0x1800073c4`
- `0x180008d9c`
- `0x180009178`
- `0x18000919c`
- `0x18000926c`
- `0x18000c650`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000931b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000931b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000932f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000932f`

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
    memset(v18, 0, v15 - (_BYTE *)v18);
  }
}

```

## disassembly

```asm
0x18000926c  push    rbx
0x18000926e  push    rbp
0x18000926f  push    rsi
0x180009270  push    rdi
0x180009271  push    r12
0x180009273  push    r13
0x180009275  push    r14
0x180009277  push    r15
0x180009279  sub     rsp, 28h
0x18000927d  mov     [rcx+4], r8d
0x180009281  lea     r14, [rcx+38h]
0x180009285  mov     eax, [rdx+8]
0x180009288  mov     rsi, rcx
0x18000928b  mov     [rcx+8], eax
0x18000928e  mov     r15, rdx
0x180009291  mov     qword ptr [rcx+10h], 0
0x180009299  movzx   eax, word ptr [rdx+40h]
0x18000929d  mov     [rcx+18h], ax
0x1800092a1  mov     al, [rdx]
0x1800092a3  mov     [rcx+1Ah], al
0x1800092a6  mov     qword ptr [rcx+20h], 0
0x1800092ae  mov     rax, [rdx+88h]
0x1800092b5  mov     [rcx+28h], rax
0x1800092b9  mov     rax, [rdx+90h]
0x1800092c0  mov     [rcx+30h], rax
0x1800092c4  mov     qword ptr [r14], 0
0x1800092cb  mov     rcx, [rdx+18h]; this
0x1800092cf  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800092d4  mov     rcx, [r15+38h]; this
0x1800092d8  mov     rbp, rax
0x1800092db  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800092e0  mov     rcx, [r15+80h]; this
0x1800092e7  add     rbp, rax
0x1800092ea  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1800092ef  add     rbp, rax
0x1800092f2  lea     rdi, [rsi+48h]
0x1800092f6  cmp     qword ptr [rsi+40h], 0
0x1800092fb  jz      short loc_180009302
0x1800092fd  cmp     [rdi], rbp
0x180009300  jnb     short loc_180009346
0x180009302  mov     rdx, rbp; dwBytes
0x180009305  mov     ecx, 8; dwFlags
0x18000930a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000930f  mov     r14, rax
0x180009312  test    rax, rax
0x180009315  jz      short loc_180009342
0x180009317  mov     rbx, [rsi+40h]
0x18000931b  call    cs:__imp_GetProcessHeap
0x180009322  nop     dword ptr [rax+rax+00h]
0x180009327  mov     r8, rbx; lpMem
0x18000932a  xor     edx, edx; dwFlags
0x18000932c  mov     rcx, rax; hHeap
0x18000932f  call    cs:__imp_HeapFree
0x180009336  nop     dword ptr [rax+rax+00h]
0x18000933b  mov     [rsi+40h], r14
0x18000933f  mov     [rdi], rbp
0x180009342  lea     r14, [rsi+38h]
0x180009346  mov     rcx, [rsi+40h]; Destination
0x18000934a  test    rcx, rcx
0x18000934d  jz      short loc_18000939D
0x18000934f  mov     rbx, [rdi]
0x180009352  lea     r9, [rsi+10h]
0x180009356  mov     r8, [r15+38h]
0x18000935a  add     rbx, rcx
0x18000935d  mov     rdx, rbx
0x180009360  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180009365  mov     r8, [r15+80h]
0x18000936c  lea     r9, [rsi+20h]
0x180009370  mov     rdx, rbx
0x180009373  mov     rcx, rax; Destination
0x180009376  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000937b  mov     r8, [r15+18h]
0x18000937f  mov     r9, r14
0x180009382  mov     rdx, rbx
0x180009385  mov     rcx, rax; Destination
0x180009388  call    ??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z; wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)
0x18000938d  sub     rbx, rax
0x180009390  xor     edx, edx; Val
0x180009392  mov     r8, rbx; Size
0x180009395  mov     rcx, rax; void *
0x180009398  call    memset
0x18000939d  add     rsp, 28h
0x1800093a1  pop     r15
0x1800093a3  pop     r14
0x1800093a5  pop     r13
0x1800093a7  pop     r12
0x1800093a9  pop     rdi
0x1800093aa  pop     rsi
0x1800093ab  pop     rbp
0x1800093ac  pop     rbx
0x1800093ad  retn
```

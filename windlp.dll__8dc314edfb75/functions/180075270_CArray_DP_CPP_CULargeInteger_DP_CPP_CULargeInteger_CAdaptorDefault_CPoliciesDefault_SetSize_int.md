# CArray<DP_CPP<CULargeInteger>,DP_CPP<CULargeInteger>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)

- ea: `0x180075270`
- end: `0x1800753b5`
- name: `?SetSize@?$CArray@V?$DP_CPP@VCULargeInteger@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z`
- size: `325`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180045b20`
- `0x180047a78`

## callees

- `0x180001be8`
- `0x18000aba4`
- `0x18001fd60`
- `0x180075270`
- `0x18007ec82`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800752ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180075356`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007538e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800752ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180075356`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007538e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800752b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800752b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180075364`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007539c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180075364`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007539c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180075321`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180075321`

## pseudocode

```c
__int64 __fastcall CArray<DP_CPP<CULargeInteger>,DP_CPP<CULargeInteger>,CAdaptorDefault,CPoliciesDefault>::SetSize(
        __int64 a1,
        int a2)
{
  __int64 v2; // rsi
  void *v3; // rbx
  int v5; // ebp
  HANDLE v6; // rax
  void *v7; // rax
  unsigned int v8; // edi
  void *v9; // r15
  int v10; // r15d
  __int64 *v11; // r12
  __int64 v12; // r14
  void *v13; // r14
  HANDLE ProcessHeap; // rax
  void *v15; // rax

  v2 = a2;
  v3 = 0;
  if ( *(_DWORD *)a1 == a2 )
  {
LABEL_23:
    v8 = 0;
    goto LABEL_24;
  }
  v5 = *(_DWORD *)(a1 + 4);
  if ( a2 < v5 )
    v5 = a2;
  if ( a2 <= 0 )
  {
LABEL_9:
    v9 = v3;
    if ( (int)v2 < *(_DWORD *)(a1 + 4) )
    {
      v10 = v2;
      do
      {
        v11 = (__int64 *)(*(_QWORD *)(a1 + 8) + 8LL * v10);
        if ( v11 )
        {
          v12 = *v11;
          if ( *v11 )
          {
            if ( *(_DWORD *)(v12 + 56) )
            {
              DeleteCriticalSection((LPCRITICAL_SECTION)(v12 + 16));
              *(_DWORD *)(v12 + 56) = 0;
            }
            operator delete((void *)v12);
            *v11 = 0;
          }
        }
        ++v10;
      }
      while ( v10 < *(_DWORD *)(a1 + 4) );
      v9 = v3;
    }
    v13 = *(void **)(a1 + 8);
    if ( v13 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v13);
      *(_QWORD *)(a1 + 8) = 0;
    }
    v15 = 0;
    if ( v3 )
      v15 = v9;
    *(_QWORD *)(a1 + 8) = v15;
    *(_DWORD *)(a1 + 4) = v5;
    *(_DWORD *)a1 = v2;
    goto LABEL_23;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v6 = GetProcessHeap();
  v7 = HeapAlloc(v6, 0, 8 * v2);
  v3 = v7;
  if ( v7 )
  {
    if ( v5 )
      memcpy_0(v7, *(const void **)(a1 + 8), 8LL * v5);
    goto LABEL_9;
  }
  v8 = -2147024882;
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024882);
LABEL_24:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  return v8;
}

```

## disassembly

```asm
0x180075270  push    rbx
0x180075272  push    rbp
0x180075273  push    rsi
0x180075274  push    rdi
0x180075275  push    r12
0x180075277  push    r13
0x180075279  push    r14
0x18007527b  push    r15
0x18007527d  sub     rsp, 28h
0x180075281  movsxd  rsi, edx
0x180075284  xor     ebx, ebx
0x180075286  mov     rdi, rcx
0x180075289  cmp     [rcx], esi
0x18007528b  jz      loc_180075380
0x180075291  mov     ebp, [rcx+4]
0x180075294  cmp     esi, ebp
0x180075296  cmovl   ebp, esi
0x180075299  test    edx, edx
0x18007529b  jle     short loc_1800752EF
0x18007529d  xor     ecx, ecx
0x18007529f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800752a4  mov     rbx, rsi
0x1800752a7  shl     rbx, 3
0x1800752ab  call    cs:__imp_GetProcessHeap
0x1800752b1  mov     r8, rbx; dwBytes
0x1800752b4  xor     edx, edx; dwFlags
0x1800752b6  mov     rcx, rax; hHeap
0x1800752b9  call    cs:__imp_HeapAlloc
0x1800752bf  mov     rbx, rax
0x1800752c2  test    rax, rax
0x1800752c5  jnz     short loc_1800752D8
0x1800752c7  mov     edi, 8007000Eh
0x1800752cc  mov     ecx, edi
0x1800752ce  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800752d3  jmp     loc_180075382
0x1800752d8  test    ebp, ebp
0x1800752da  jz      short loc_1800752EF
0x1800752dc  mov     rdx, [rdi+8]; Src
0x1800752e0  mov     rcx, rax; void *
0x1800752e3  movsxd  r8, ebp
0x1800752e6  shl     r8, 3; Size
0x1800752ea  call    memcpy_0
0x1800752ef  mov     r13, rbx
0x1800752f2  mov     r15, rbx
0x1800752f5  cmp     esi, [rdi+4]
0x1800752f8  jge     short loc_18007534B
0x1800752fa  mov     r15d, esi
0x1800752fd  mov     rcx, [rdi+8]
0x180075301  movsxd  rax, r15d
0x180075304  lea     r12, [rcx+rax*8]
0x180075308  test    r12, r12
0x18007530b  jz      short loc_18007533F
0x18007530d  mov     r14, [r12]
0x180075311  test    r14, r14
0x180075314  jz      short loc_18007533F
0x180075316  cmp     dword ptr [r14+38h], 0
0x18007531b  jz      short loc_18007532F
0x18007531d  lea     rcx, [r14+10h]; lpCriticalSection
0x180075321  call    cs:__imp_DeleteCriticalSection
0x180075327  mov     dword ptr [r14+38h], 0
0x18007532f  mov     rcx, r14; Block
0x180075332  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180075337  mov     qword ptr [r12], 0
0x18007533f  inc     r15d
0x180075342  cmp     r15d, [rdi+4]
0x180075346  jl      short loc_1800752FD
0x180075348  mov     r15, rbx
0x18007534b  mov     r14, [rdi+8]
0x18007534f  xor     ebx, ebx
0x180075351  test    r14, r14
0x180075354  jz      short loc_18007536E
0x180075356  call    cs:__imp_GetProcessHeap
0x18007535c  mov     r8, r14; lpMem
0x18007535f  xor     edx, edx; dwFlags
0x180075361  mov     rcx, rax; hHeap
0x180075364  call    cs:__imp_HeapFree
0x18007536a  mov     [rdi+8], rbx
0x18007536e  xor     eax, eax
0x180075370  test    r13, r13
0x180075373  cmovnz  rax, r15
0x180075377  mov     [rdi+8], rax
0x18007537b  mov     [rdi+4], ebp
0x18007537e  mov     [rdi], esi
0x180075380  xor     edi, edi
0x180075382  mov     ecx, edi
0x180075384  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180075389  test    rbx, rbx
0x18007538c  jz      short loc_1800753A2
0x18007538e  call    cs:__imp_GetProcessHeap
0x180075394  mov     r8, rbx; lpMem
0x180075397  xor     edx, edx; dwFlags
0x180075399  mov     rcx, rax; hHeap
0x18007539c  call    cs:__imp_HeapFree
0x1800753a2  mov     eax, edi
0x1800753a4  add     rsp, 28h
0x1800753a8  pop     r15
0x1800753aa  pop     r14
0x1800753ac  pop     r13
0x1800753ae  pop     r12
0x1800753b0  pop     rdi
0x1800753b1  pop     rsi
0x1800753b2  pop     rbp
0x1800753b3  pop     rbx
0x1800753b4  retn
```

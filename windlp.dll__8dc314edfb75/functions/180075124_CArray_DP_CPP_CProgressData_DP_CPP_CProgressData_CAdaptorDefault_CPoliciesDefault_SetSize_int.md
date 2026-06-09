# CArray<DP_CPP<CProgressData>,DP_CPP<CProgressData>,CAdaptorDefault,CPoliciesDefault>::SetSize(int)

- ea: `0x180075124`
- end: `0x180075269`
- name: `?SetSize@?$CArray@V?$DP_CPP@VCProgressData@@@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z`
- size: `325`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18004633c`
- `0x1800478c0`
- `0x180059134`
- `0x180064ae8`
- `0x18006e560`
- `0x18007c824`

## callees

- `0x180001be8`
- `0x18000aba4`
- `0x18001fd60`
- `0x180075124`
- `0x18007ec82`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007515f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007520a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180075242`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007515f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007520a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180075242`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007516d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007516d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180075218`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180075250`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180075218`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180075250`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800751d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800751d5`

## pseudocode

```c
__int64 __fastcall CArray<DP_CPP<CProgressData>,DP_CPP<CProgressData>,CAdaptorDefault,CPoliciesDefault>::SetSize(
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
            if ( *(_DWORD *)(v12 + 72) )
            {
              DeleteCriticalSection((LPCRITICAL_SECTION)(v12 + 32));
              *(_DWORD *)(v12 + 72) = 0;
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
0x180075124  push    rbx
0x180075126  push    rbp
0x180075127  push    rsi
0x180075128  push    rdi
0x180075129  push    r12
0x18007512b  push    r13
0x18007512d  push    r14
0x18007512f  push    r15
0x180075131  sub     rsp, 28h
0x180075135  movsxd  rsi, edx
0x180075138  xor     ebx, ebx
0x18007513a  mov     rdi, rcx
0x18007513d  cmp     [rcx], esi
0x18007513f  jz      loc_180075234
0x180075145  mov     ebp, [rcx+4]
0x180075148  cmp     esi, ebp
0x18007514a  cmovl   ebp, esi
0x18007514d  test    edx, edx
0x18007514f  jle     short loc_1800751A3
0x180075151  xor     ecx, ecx
0x180075153  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180075158  mov     rbx, rsi
0x18007515b  shl     rbx, 3
0x18007515f  call    cs:__imp_GetProcessHeap
0x180075165  mov     r8, rbx; dwBytes
0x180075168  xor     edx, edx; dwFlags
0x18007516a  mov     rcx, rax; hHeap
0x18007516d  call    cs:__imp_HeapAlloc
0x180075173  mov     rbx, rax
0x180075176  test    rax, rax
0x180075179  jnz     short loc_18007518C
0x18007517b  mov     edi, 8007000Eh
0x180075180  mov     ecx, edi
0x180075182  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180075187  jmp     loc_180075236
0x18007518c  test    ebp, ebp
0x18007518e  jz      short loc_1800751A3
0x180075190  mov     rdx, [rdi+8]; Src
0x180075194  mov     rcx, rax; void *
0x180075197  movsxd  r8, ebp
0x18007519a  shl     r8, 3; Size
0x18007519e  call    memcpy_0
0x1800751a3  mov     r13, rbx
0x1800751a6  mov     r15, rbx
0x1800751a9  cmp     esi, [rdi+4]
0x1800751ac  jge     short loc_1800751FF
0x1800751ae  mov     r15d, esi
0x1800751b1  mov     rcx, [rdi+8]
0x1800751b5  movsxd  rax, r15d
0x1800751b8  lea     r12, [rcx+rax*8]
0x1800751bc  test    r12, r12
0x1800751bf  jz      short loc_1800751F3
0x1800751c1  mov     r14, [r12]
0x1800751c5  test    r14, r14
0x1800751c8  jz      short loc_1800751F3
0x1800751ca  cmp     dword ptr [r14+48h], 0
0x1800751cf  jz      short loc_1800751E3
0x1800751d1  lea     rcx, [r14+20h]; lpCriticalSection
0x1800751d5  call    cs:__imp_DeleteCriticalSection
0x1800751db  mov     dword ptr [r14+48h], 0
0x1800751e3  mov     rcx, r14; Block
0x1800751e6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800751eb  mov     qword ptr [r12], 0
0x1800751f3  inc     r15d
0x1800751f6  cmp     r15d, [rdi+4]
0x1800751fa  jl      short loc_1800751B1
0x1800751fc  mov     r15, rbx
0x1800751ff  mov     r14, [rdi+8]
0x180075203  xor     ebx, ebx
0x180075205  test    r14, r14
0x180075208  jz      short loc_180075222
0x18007520a  call    cs:__imp_GetProcessHeap
0x180075210  mov     r8, r14; lpMem
0x180075213  xor     edx, edx; dwFlags
0x180075215  mov     rcx, rax; hHeap
0x180075218  call    cs:__imp_HeapFree
0x18007521e  mov     [rdi+8], rbx
0x180075222  xor     eax, eax
0x180075224  test    r13, r13
0x180075227  cmovnz  rax, r15
0x18007522b  mov     [rdi+8], rax
0x18007522f  mov     [rdi+4], ebp
0x180075232  mov     [rdi], esi
0x180075234  xor     edi, edi
0x180075236  mov     ecx, edi
0x180075238  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007523d  test    rbx, rbx
0x180075240  jz      short loc_180075256
0x180075242  call    cs:__imp_GetProcessHeap
0x180075248  mov     r8, rbx; lpMem
0x18007524b  xor     edx, edx; dwFlags
0x18007524d  mov     rcx, rax; hHeap
0x180075250  call    cs:__imp_HeapFree
0x180075256  mov     eax, edi
0x180075258  add     rsp, 28h
0x18007525c  pop     r15
0x18007525e  pop     r14
0x180075260  pop     r13
0x180075262  pop     r12
0x180075264  pop     rdi
0x180075265  pop     rsi
0x180075266  pop     rbp
0x180075267  pop     rbx
0x180075268  retn
```

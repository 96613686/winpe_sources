# CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::Reset(void)

- ea: `0x1800398b4`
- end: `0x1800399bd`
- name: `?Reset@?$CAsyncOperationT@VCSmartCardDetector@CTokenActivation@@$00VCRefCountImpl@@$0A@@@AEAAJXZ`
- size: `265`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180037288`
- `0x18003a474`

## callees

- `0x180003398`
- `0x180004288`
- `0x1800398b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800398ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003997b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800398ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003997b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039903`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003998f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039903`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003998f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003991f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003996b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003991f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003996b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18003993d`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18003993d`

## pseudocode

```c
__int64 __fastcall CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::Reset(__int64 a1)
{
  __int64 v1; // rax
  void *v3; // r14
  __int64 v4; // rdi
  DH_HANDLE *i; // rsi
  HANDLE ProcessHeap; // rax
  void *v7; // rcx
  _QWORD *v8; // rdi
  void *v9; // rcx
  HANDLE v10; // rax

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = (void *)(v1 - 8);
    v4 = *(_QWORD *)(v1 - 8);
    for ( i = (DH_HANDLE *)(v1 + 8 * v4); v4; --v4 )
    {
      i = (DH_HANDLE *)((char *)i - 8);
      DH_HANDLE::~DH_HANDLE(i);
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    *(_QWORD *)(a1 + 8) = 0;
  }
  *(_DWORD *)(a1 + 40) = 0;
  v7 = *(void **)(a1 + 32);
  if ( v7 )
  {
    CloseHandle(v7);
    *(_QWORD *)(a1 + 32) = 0;
  }
  *(_DWORD *)(a1 + 44) = 0;
  *(_DWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 52) = 0;
  *(_DWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = EncodePointer(0);
  v8 = *(_QWORD **)(a1 + 72);
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
    {
      v9 = (void *)v8[1];
      if ( v9 )
      {
        CloseHandle(v9);
        v8[1] = 0;
      }
      v10 = GetProcessHeap();
      HeapFree(v10, 0, v8);
    }
    *(_QWORD *)(a1 + 72) = 0;
  }
  *(_DWORD *)(a1 + 20) = 0;
  *(_DWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 16) = 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  return 0;
}

```

## disassembly

```asm
0x1800398b4  push    rbx
0x1800398b6  push    rbp
0x1800398b7  push    rsi
0x1800398b8  push    rdi
0x1800398b9  push    r14
0x1800398bb  sub     rsp, 20h
0x1800398bf  mov     rax, [rcx+8]
0x1800398c3  xor     ebp, ebp
0x1800398c5  mov     rbx, rcx
0x1800398c8  test    rax, rax
0x1800398cb  jz      short loc_180039913
0x1800398cd  lea     r14, [rax-8]
0x1800398d1  mov     rdi, [r14]
0x1800398d4  lea     rsi, [rax+rdi*8]
0x1800398d8  test    rdi, rdi
0x1800398db  jz      short loc_1800398EF
0x1800398dd  sub     rsi, 8
0x1800398e1  mov     rcx, rsi; this
0x1800398e4  call    ??1DH_HANDLE@@QEAA@XZ; DH_HANDLE::~DH_HANDLE(void)
0x1800398e9  sub     rdi, 1
0x1800398ed  jnz     short loc_1800398DD
0x1800398ef  call    cs:__imp_GetProcessHeap
0x1800398f6  nop     dword ptr [rax+rax+00h]
0x1800398fb  mov     r8, r14; lpMem
0x1800398fe  xor     edx, edx; dwFlags
0x180039900  mov     rcx, rax; hHeap
0x180039903  call    cs:__imp_HeapFree
0x18003990a  nop     dword ptr [rax+rax+00h]
0x18003990f  mov     [rbx+8], rbp
0x180039913  mov     [rbx+28h], ebp
0x180039916  mov     rcx, [rbx+20h]; hObject
0x18003991a  test    rcx, rcx
0x18003991d  jz      short loc_18003992F
0x18003991f  call    cs:__imp_CloseHandle
0x180039926  nop     dword ptr [rax+rax+00h]
0x18003992b  mov     [rbx+20h], rbp
0x18003992f  mov     [rbx+2Ch], ebp
0x180039932  xor     ecx, ecx; Ptr
0x180039934  mov     [rbx+30h], ebp
0x180039937  mov     [rbx+34h], ebp
0x18003993a  mov     [rbx+38h], ebp
0x18003993d  call    cs:__imp_EncodePointer
0x180039944  nop     dword ptr [rax+rax+00h]
0x180039949  mov     [rbx+40h], rax
0x18003994d  mov     rdi, [rbx+48h]
0x180039951  test    rdi, rdi
0x180039954  jz      short loc_18003999F
0x180039956  or      eax, 0FFFFFFFFh
0x180039959  lock xadd [rdi], eax
0x18003995d  cmp     eax, 1
0x180039960  jnz     short loc_18003999B
0x180039962  mov     rcx, [rdi+8]; hObject
0x180039966  test    rcx, rcx
0x180039969  jz      short loc_18003997B
0x18003996b  call    cs:__imp_CloseHandle
0x180039972  nop     dword ptr [rax+rax+00h]
0x180039977  mov     [rdi+8], rbp
0x18003997b  call    cs:__imp_GetProcessHeap
0x180039982  nop     dword ptr [rax+rax+00h]
0x180039987  mov     r8, rdi; lpMem
0x18003998a  xor     edx, edx; dwFlags
0x18003998c  mov     rcx, rax; hHeap
0x18003998f  call    cs:__imp_HeapFree
0x180039996  nop     dword ptr [rax+rax+00h]
0x18003999b  mov     [rbx+48h], rbp
0x18003999f  mov     [rbx+14h], ebp
0x1800399a2  mov     [rbx+18h], ebp
0x1800399a5  mov     [rbx+10h], ebp
0x1800399a8  xor     ecx, ecx
0x1800399aa  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800399af  xor     eax, eax
0x1800399b1  add     rsp, 20h
0x1800399b5  pop     r14
0x1800399b7  pop     rdi
0x1800399b8  pop     rsi
0x1800399b9  pop     rbp
0x1800399ba  pop     rbx
0x1800399bb  retn
```

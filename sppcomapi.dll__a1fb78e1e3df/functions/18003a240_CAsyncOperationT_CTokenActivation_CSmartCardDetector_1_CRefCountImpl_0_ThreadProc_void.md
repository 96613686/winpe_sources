# CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::ThreadProc(void *)

- ea: `0x18003a240`
- end: `0x18003a39f`
- name: `?ThreadProc@?$CAsyncOperationT@VCSmartCardDetector@CTokenActivation@@$00VCRefCountImpl@@$0A@@@CAKPEAX@Z`
- size: `351`
- prototype: `__int64 __fastcall(CTokenActivation::CSmartCardDetector *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18001a134`
- `0x180037050`
- `0x180039398`
- `0x18003a240`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a360`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a360`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a374`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003a374`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a343`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a343`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a25b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003a25b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a2d0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a319`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a2d0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a319`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a385`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a385`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003a28a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003a29f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003a28a`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18003a29f`

## pseudocode

```c
__int64 __fastcall CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::ThreadProc(
        CTokenActivation::CSmartCardDetector *this)
{
  int v2; // edi
  void *v3; // rcx
  __int64 (__fastcall *v4)(CTokenActivation::CSmartCardDetector *); // rax
  __int64 v5; // rcx
  __int64 v6; // rcx
  void *v7; // rcx
  HANDLE ProcessHeap; // rax

  LOWORD(v2) = 0;
  v3 = (void *)*((_QWORD *)this + 4);
  if ( v3 )
    WaitForSingleObject(v3, 0xFFFFFFFF);
  while ( (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)this + 14, 1u) < *((_DWORD *)this + 13)
       && !*((_DWORD *)this + 5)
       && !*((_DWORD *)this + 6) )
  {
    if ( DecodePointer(*((PVOID *)this + 8)) )
    {
      v4 = (__int64 (__fastcall *)(CTokenActivation::CSmartCardDetector *))DecodePointer(*((PVOID *)this + 8));
      v2 = v4(this);
    }
    else
    {
      v2 = CTokenActivation::CSmartCardDetector::Invoke(this);
      if ( v2 == -2147467263 )
        goto LABEL_9;
    }
    if ( v2 < 0 )
    {
LABEL_9:
      v5 = *((_QWORD *)this + 9);
      *((_DWORD *)this + 4) = v2;
      *((_DWORD *)this + 5) = 1;
      if ( v5 )
        SetEvent(*(HANDLE *)(v5 + 8));
    }
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 12, 0xFFFFFFFF) == 1 && !*((_DWORD *)this + 5) )
  {
    v6 = *((_QWORD *)this + 9);
    *((_DWORD *)this + 5) = 1;
    if ( v6 )
      SetEvent(*(HANDLE *)(v6 + 8));
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this, 0xFFFFFFFF) == 1 )
  {
    SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>::~SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>((char *)this + 72);
    v7 = (void *)*((_QWORD *)this + 4);
    if ( v7 )
    {
      CloseHandle(v7);
      *((_QWORD *)this + 4) = 0;
    }
    SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>::~SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>((char *)this + 8);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, this);
  }
  SetLastError((unsigned __int16)v2);
  return (unsigned __int16)v2;
}

```

## disassembly

```asm
0x18003a240  mov     [rsp+arg_8], rbx
0x18003a245  push    rdi
0x18003a246  sub     rsp, 20h
0x18003a24a  mov     rbx, rcx
0x18003a24d  xor     edi, edi
0x18003a24f  mov     rcx, [rcx+20h]; hHandle
0x18003a253  test    rcx, rcx
0x18003a256  jz      short loc_18003A267
0x18003a258  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003a25b  call    cs:__imp_WaitForSingleObject
0x18003a262  nop     dword ptr [rax+rax+00h]
0x18003a267  mov     eax, 1
0x18003a26c  lock xadd [rbx+38h], eax
0x18003a271  mov     ecx, [rbx+34h]
0x18003a274  cmp     eax, ecx
0x18003a276  jnb     short loc_18003A2F1
0x18003a278  mov     eax, [rbx+14h]
0x18003a27b  test    eax, eax
0x18003a27d  jnz     short loc_18003A2F1
0x18003a27f  mov     eax, [rbx+18h]
0x18003a282  test    eax, eax
0x18003a284  jnz     short loc_18003A2F1
0x18003a286  mov     rcx, [rbx+40h]; Ptr
0x18003a28a  call    cs:__imp_DecodePointer
0x18003a291  nop     dword ptr [rax+rax+00h]
0x18003a296  test    rax, rax
0x18003a299  jz      short loc_18003A2DE
0x18003a29b  mov     rcx, [rbx+40h]; Ptr
0x18003a29f  call    cs:__imp_DecodePointer
0x18003a2a6  nop     dword ptr [rax+rax+00h]
0x18003a2ab  mov     rcx, rbx
0x18003a2ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2b3  mov     edi, eax
0x18003a2b5  test    edi, edi
0x18003a2b7  jns     short loc_18003A267
0x18003a2b9  mov     rcx, [rbx+48h]
0x18003a2bd  mov     [rbx+10h], edi
0x18003a2c0  mov     dword ptr [rbx+14h], 1
0x18003a2c7  test    rcx, rcx
0x18003a2ca  jz      short loc_18003A267
0x18003a2cc  mov     rcx, [rcx+8]; hEvent
0x18003a2d0  call    cs:__imp_SetEvent
0x18003a2d7  nop     dword ptr [rax+rax+00h]
0x18003a2dc  jmp     short loc_18003A267
0x18003a2de  mov     rcx, rbx; this
0x18003a2e1  call    ?Invoke@CSmartCardDetector@CTokenActivation@@QEAAJXZ; CTokenActivation::CSmartCardDetector::Invoke(void)
0x18003a2e6  mov     edi, eax
0x18003a2e8  cmp     eax, 80004001h
0x18003a2ed  jnz     short loc_18003A2B5
0x18003a2ef  jmp     short loc_18003A2B9
0x18003a2f1  or      eax, 0FFFFFFFFh
0x18003a2f4  lock xadd [rbx+30h], eax
0x18003a2f9  cmp     eax, 1
0x18003a2fc  jnz     short loc_18003A325
0x18003a2fe  mov     eax, [rbx+14h]
0x18003a301  test    eax, eax
0x18003a303  jnz     short loc_18003A325
0x18003a305  mov     rcx, [rbx+48h]
0x18003a309  mov     dword ptr [rbx+14h], 1
0x18003a310  test    rcx, rcx
0x18003a313  jz      short loc_18003A325
0x18003a315  mov     rcx, [rcx+8]; hEvent
0x18003a319  call    cs:__imp_SetEvent
0x18003a320  nop     dword ptr [rax+rax+00h]
0x18003a325  or      eax, 0FFFFFFFFh
0x18003a328  lock xadd [rbx], eax
0x18003a32c  cmp     eax, 1
0x18003a32f  jnz     short loc_18003A380
0x18003a331  lea     rcx, [rbx+48h]
0x18003a335  call    ??1?$SP@V?$CRefCountWrapper@VDH_HANDLE@@@@V?$SP_COM@V?$CRefCountWrapper@VDH_HANDLE@@@@@@@@QEAA@XZ; SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>::~SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>(void)
0x18003a33a  mov     rcx, [rbx+20h]; hObject
0x18003a33e  test    rcx, rcx
0x18003a341  jz      short loc_18003A357
0x18003a343  call    cs:__imp_CloseHandle
0x18003a34a  nop     dword ptr [rax+rax+00h]
0x18003a34f  mov     qword ptr [rbx+20h], 0
0x18003a357  lea     rcx, [rbx+8]
0x18003a35b  call    ??1?$SP@VDH_HANDLE@@V?$SP_CPP_ARRAY@VDH_HANDLE@@@@@@QEAA@XZ; SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>::~SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>(void)
0x18003a360  call    cs:__imp_GetProcessHeap
0x18003a367  nop     dword ptr [rax+rax+00h]
0x18003a36c  mov     r8, rbx; lpMem
0x18003a36f  xor     edx, edx; dwFlags
0x18003a371  mov     rcx, rax; hHeap
0x18003a374  call    cs:__imp_HeapFree
0x18003a37b  nop     dword ptr [rax+rax+00h]
0x18003a380  movzx   ebx, di
0x18003a383  mov     ecx, ebx; dwErrCode
0x18003a385  call    cs:__imp_SetLastError
0x18003a38c  nop     dword ptr [rax+rax+00h]
0x18003a391  mov     eax, ebx
0x18003a393  mov     rbx, [rsp+28h+arg_8]
0x18003a398  add     rsp, 20h
0x18003a39c  pop     rdi
0x18003a39d  retn
```

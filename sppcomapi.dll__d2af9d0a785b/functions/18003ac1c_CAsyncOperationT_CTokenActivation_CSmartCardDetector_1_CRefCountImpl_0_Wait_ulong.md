# CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::Wait(ulong)

- ea: `0x18003ac1c`
- end: `0x18003ad1c`
- name: `?Wait@?$CAsyncOperationT@VCSmartCardDetector@CTokenActivation@@$00VCRefCountImpl@@$0A@@@AEAAJK@Z`
- size: `256`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180037288`
- `0x18003a474`

## callees

- `0x180003398`
- `0x180003520`
- `0x180004288`
- `0x18003ac1c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003acda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003acda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003acee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003acee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ac75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ac75`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18003ac53`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18003ac53`

## pseudocode

```c
__int64 __fastcall CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::Wait(__int64 a1)
{
  DWORD v2; // eax
  unsigned int v3; // ebx
  signed int LastError; // eax
  __int64 v5; // rax
  void *v6; // r14
  __int64 v7; // rsi
  DH_HANDLE *i; // rbp
  HANDLE ProcessHeap; // rax

  if ( !*(_QWORD *)(a1 + 8) || !*(_DWORD *)(a1 + 40) )
  {
    v3 = 0;
    goto LABEL_21;
  }
  v2 = WaitForMultipleObjects(*(_DWORD *)(a1 + 40), *(const HANDLE **)(a1 + 8), 1, 0xFFFFFFFF);
  if ( v2 )
  {
    if ( v2 == 258 )
    {
      v3 = -2147023436;
      goto LABEL_14;
    }
    if ( v2 != -1 )
    {
      v3 = -2147418113;
LABEL_14:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
      goto LABEL_21;
    }
    LastError = GetLastError();
    v3 = LastError;
    if ( !LastError )
    {
      v3 = -2147467259;
      goto LABEL_14;
    }
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( (v3 & 0x80000000) != 0 )
      goto LABEL_14;
  }
  else
  {
    v5 = *(_QWORD *)(a1 + 8);
    v3 = 0;
    if ( v5 )
    {
      v6 = (void *)(v5 - 8);
      v7 = *(_QWORD *)(v5 - 8);
      for ( i = (DH_HANDLE *)(v5 + 8 * v7); v7; --v7 )
      {
        i = (DH_HANDLE *)((char *)i - 8);
        DH_HANDLE::~DH_HANDLE(i);
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
      *(_QWORD *)(a1 + 8) = 0;
    }
    _InterlockedExchange((volatile __int32 *)(a1 + 40), 0);
  }
LABEL_21:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  return v3;
}

```

## disassembly

```asm
0x18003ac1c  push    rbx
0x18003ac1e  push    rbp
0x18003ac1f  push    rsi
0x18003ac20  push    rdi
0x18003ac21  push    r14
0x18003ac23  sub     rsp, 20h
0x18003ac27  cmp     qword ptr [rcx+8], 0
0x18003ac2c  mov     rdi, rcx
0x18003ac2f  jz      loc_18003AD05
0x18003ac35  mov     eax, [rcx+28h]
0x18003ac38  test    eax, eax
0x18003ac3a  jz      loc_18003AD05
0x18003ac40  mov     rdx, [rcx+8]; lpHandles
0x18003ac44  or      ebx, 0FFFFFFFFh
0x18003ac47  mov     ecx, [rcx+28h]; nCount
0x18003ac4a  mov     r9d, ebx; dwMilliseconds
0x18003ac4d  mov     r8d, 1; bWaitAll
0x18003ac53  call    cs:__imp_WaitForMultipleObjects
0x18003ac5a  nop     dword ptr [rax+rax+00h]
0x18003ac5f  test    eax, eax
0x18003ac61  jz      short loc_18003ACAD
0x18003ac63  cmp     eax, 102h
0x18003ac68  jz      short loc_18003AC9F
0x18003ac6a  cmp     eax, ebx
0x18003ac6c  jz      short loc_18003AC75
0x18003ac6e  mov     ebx, 8000FFFFh
0x18003ac73  jmp     short loc_18003ACA4
0x18003ac75  call    cs:__imp_GetLastError
0x18003ac7c  nop     dword ptr [rax+rax+00h]
0x18003ac81  mov     ebx, eax
0x18003ac83  test    eax, eax
0x18003ac85  jnz     short loc_18003AC8E
0x18003ac87  mov     ebx, 80004005h
0x18003ac8c  jmp     short loc_18003ACA4
0x18003ac8e  jle     short loc_18003AC99
0x18003ac90  movzx   ebx, ax
0x18003ac93  or      ebx, 80070000h
0x18003ac99  test    ebx, ebx
0x18003ac9b  jns     short loc_18003AD07
0x18003ac9d  jmp     short loc_18003ACA4
0x18003ac9f  mov     ebx, 800705B4h
0x18003aca4  mov     ecx, ebx
0x18003aca6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003acab  jmp     short loc_18003AD07
0x18003acad  mov     rax, [rdi+8]
0x18003acb1  xor     ebx, ebx
0x18003acb3  test    rax, rax
0x18003acb6  jz      short loc_18003ACFE
0x18003acb8  lea     r14, [rax-8]
0x18003acbc  mov     rsi, [r14]
0x18003acbf  lea     rbp, [rax+rsi*8]
0x18003acc3  test    rsi, rsi
0x18003acc6  jz      short loc_18003ACDA
0x18003acc8  sub     rbp, 8
0x18003accc  mov     rcx, rbp; this
0x18003accf  call    ??1DH_HANDLE@@QEAA@XZ; DH_HANDLE::~DH_HANDLE(void)
0x18003acd4  sub     rsi, 1
0x18003acd8  jnz     short loc_18003ACC8
0x18003acda  call    cs:__imp_GetProcessHeap
0x18003ace1  nop     dword ptr [rax+rax+00h]
0x18003ace6  mov     r8, r14; lpMem
0x18003ace9  xor     edx, edx; dwFlags
0x18003aceb  mov     rcx, rax; hHeap
0x18003acee  call    cs:__imp_HeapFree
0x18003acf5  nop     dword ptr [rax+rax+00h]
0x18003acfa  mov     [rdi+8], rbx
0x18003acfe  xor     eax, eax
0x18003ad00  xchg    eax, [rdi+28h]
0x18003ad03  jmp     short loc_18003AD07
0x18003ad05  xor     ebx, ebx
0x18003ad07  mov     ecx, ebx
0x18003ad09  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003ad0e  mov     eax, ebx
0x18003ad10  add     rsp, 20h
0x18003ad14  pop     r14
0x18003ad16  pop     rdi
0x18003ad17  pop     rsi
0x18003ad18  pop     rbp
0x18003ad19  pop     rbx
0x18003ad1a  retn
```

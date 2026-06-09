# CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::BeginInvokeEx(long (*)(CTokenActivation::CSmartCardDetector *),CRefCountWrapper<DH_HANDLE> *,uint)

- ea: `0x180037288`
- end: `0x1800376ba`
- name: `?BeginInvokeEx@?$CAsyncOperationT@VCSmartCardDetector@CTokenActivation@@$00VCRefCountImpl@@$0A@@@QEAAJP6AJPEAVCSmartCardDetector@CTokenActivation@@@ZPEAV?$CRefCountWrapper@VDH_HANDLE@@@@I@Z`
- size: `1074`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18003a474`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001a134`
- `0x180036eb0`
- `0x180037050`
- `0x180037288`
- `0x1800398b4`
- `0x180039a0c`
- `0x18003ac1c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037472`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037538`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003767e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037472`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037538`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003767e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037486`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037692`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037486`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180037692`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003754c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003754c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800374cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037666`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037462`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800374cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037666`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180037600`
- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x180037600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800374e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800373d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800374e4`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800374b7`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800374b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800373b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800373b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180037301`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180037301`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800373c0`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800373c0`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180037432`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x180037432`
- `KERNEL32!GetProcessAffinityMask` at `0x180037320`
- `KERNEL32!GetProcessAffinityMask` at `0x180037320`

## pseudocode

```c
__int64 __fastcall CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::BeginInvokeEx(
        char *a1,
        ULONG_PTR a2,
        __int64 a3)
{
  _QWORD *v3; // r15
  __int64 v5; // rcx
  signed int v6; // ebx
  _QWORD **v7; // r12
  HANDLE CurrentProcess; // rax
  unsigned int v9; // esi
  signed int LastError; // eax
  ULONG_PTR v11; // rcx
  HANDLE CurrentThread; // rax
  int ThreadPriority; // r13d
  signed int v14; // eax
  _QWORD *v15; // rbx
  void *v16; // rcx
  HANDLE ProcessHeap; // rax
  __int64 v18; // rbp
  __int64 v19; // rbx
  bool v20; // cf
  SIZE_T v21; // rbx
  HANDLE v22; // rax
  _QWORD *v23; // rax
  unsigned int v24; // edx
  unsigned int (*v25)(void *); // r8
  _QWORD *v26; // rbx
  DH_HANDLE *v27; // r14
  unsigned int v28; // ebp
  int v29; // r14d
  void *v31; // rcx
  HANDLE v32; // rax
  unsigned int v33; // [rsp+20h] [rbp-68h]
  ULONG_PTR SystemAffinityMask; // [rsp+90h] [rbp+8h] BYREF
  ULONG_PTR ProcessAffinityMask; // [rsp+98h] [rbp+10h] BYREF
  int PreviousCount; // [rsp+A0h] [rbp+18h] BYREF
  int v37; // [rsp+A4h] [rbp+1Ch]
  unsigned int v38; // [rsp+A8h] [rbp+20h] BYREF

  v37 = HIDWORD(a3);
  ProcessAffinityMask = a2;
  v3 = a1 + 8;
  PreviousCount = 0;
  v38 = 0;
  if ( *((_QWORD *)a1 + 1)
    || *((_DWORD *)a1 + 10)
    || *((_QWORD *)a1 + 4)
    || *((_DWORD *)a1 + 13)
    || (v7 = (_QWORD **)(a1 + 72), *((_QWORD *)a1 + 9)) )
  {
    v5 = 2147549183LL;
    v6 = -2147418113;
LABEL_4:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_49;
  }
  ProcessAffinityMask = 0;
  SystemAffinityMask = 0;
  CurrentProcess = GetCurrentProcess();
  v9 = 0;
  if ( GetProcessAffinityMask(CurrentProcess, &ProcessAffinityMask, &SystemAffinityMask) )
  {
    v11 = ProcessAffinityMask;
    v6 = 0;
    if ( ProcessAffinityMask )
    {
      do
      {
        ++v9;
        v11 &= v11 - 1;
      }
      while ( v11 );
      ProcessAffinityMask = 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v6);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v6 >= 0 )
  {
    if ( v9 > 1 )
      v9 = 1;
  }
  else
  {
    v9 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v6);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v6 < 0 )
    goto LABEL_22;
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  if ( ThreadPriority == 0x7FFFFFFF )
  {
    ThreadPriority = 0;
    v14 = GetLastError();
    v6 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v6 = (unsigned __int16)v14 | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v6);
  }
  else
  {
    v6 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v6 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v6);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v6 < 0 )
  {
LABEL_22:
    v5 = (unsigned int)v6;
    goto LABEL_4;
  }
  *((_QWORD *)a1 + 8) = EncodePointer(0);
  v15 = *v7;
  if ( *v7 && _InterlockedExchangeAdd((volatile signed __int32 *)v15, 0xFFFFFFFF) == 1 )
  {
    v16 = (void *)v15[1];
    if ( v16 )
    {
      CloseHandle(v16);
      v15[1] = 0;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v15);
  }
  *v7 = 0;
  *((_DWORD *)a1 + 5) = 0;
  *((_DWORD *)a1 + 6) = 0;
  *((_DWORD *)a1 + 13) = 1;
  *((_DWORD *)a1 + 14) = 0;
  v18 = v9;
  v19 = 8LL * v9;
  if ( !is_mul_ok(v9, 8u) )
    v19 = -1;
  v20 = __CFADD__(v19, 8);
  v21 = v19 + 8;
  if ( v20 )
    v21 = -1;
  v22 = GetProcessHeap();
  v23 = HeapAlloc(v22, 0, v21);
  if ( !v23 )
  {
    *v3 = 0;
LABEL_62:
    v6 = -2147024882;
    v5 = 2147942414LL;
    goto LABEL_4;
  }
  *v23 = v9;
  v26 = v23 + 1;
  v27 = (DH_HANDLE *)(v23 + 1);
  if ( v9 )
  {
    do
    {
      DH_HANDLE::DH_HANDLE(v27);
      v27 = (DH_HANDLE *)((char *)v27 + 8);
      --v18;
    }
    while ( v18 );
  }
  *v3 = v26;
  if ( !v26 )
    goto LABEL_62;
  v6 = 0;
  v28 = 0;
  if ( v9 )
  {
    while ( 1 )
    {
      _InterlockedIncrement((volatile signed __int32 *)a1);
      _InterlockedIncrement((volatile signed __int32 *)a1 + 10);
      _InterlockedIncrement((volatile signed __int32 *)a1 + 11);
      _InterlockedIncrement((volatile signed __int32 *)a1 + 12);
      v29 = SafeThreadCreateEx(
              (struct _SECURITY_ATTRIBUTES *)(*v3 + 8LL * v28),
              v24,
              v25,
              a1,
              v33,
              ThreadPriority,
              &v38,
              (void **)(*v3 + 8LL * v28));
      if ( v29 < 0 )
        break;
      if ( ++v28 >= v9 )
        goto LABEL_49;
    }
    _InterlockedAdd((volatile signed __int32 *)a1 + 10, 0xFFFFFFFF);
    _InterlockedAdd((volatile signed __int32 *)a1 + 11, 0xFFFFFFFF);
    _InterlockedAdd((volatile signed __int32 *)a1 + 12, 0xFFFFFFFF);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0xFFFFFFFF) == 1 )
    {
      SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>::~SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>(v7);
      v31 = (void *)*((_QWORD *)a1 + 4);
      if ( v31 )
      {
        CloseHandle(v31);
        *((_QWORD *)a1 + 4) = 0;
      }
      SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>::~SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>(v3);
      v32 = GetProcessHeap();
      HeapFree(v32, 0, a1);
    }
    v6 = v29;
    v5 = (unsigned int)v29;
    goto LABEL_4;
  }
LABEL_49:
  if ( *((_QWORD *)a1 + 4) )
  {
    if ( v6 < 0 )
      *((_DWORD *)a1 + 6) = 1;
    ReleaseSemaphore(*((HANDLE *)a1 + 4), *((_DWORD *)a1 + 11), &PreviousCount);
  }
  if ( v6 < 0 )
  {
    CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::Wait(a1);
    CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::Reset(a1);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180037288  mov     rax, rsp
0x18003728b  mov     [rax+20h], r9d
0x18003728f  mov     [rax+18h], r8
0x180037293  mov     [rax+10h], rdx
0x180037297  push    rbx
0x180037298  push    rbp
0x180037299  push    rsi
0x18003729a  push    rdi
0x18003729b  push    r12
0x18003729d  push    r13
0x18003729f  push    r14
0x1800372a1  push    r15
0x1800372a3  sub     rsp, 48h
0x1800372a7  xor     r14d, r14d
0x1800372aa  lea     r15, [rcx+8]
0x1800372ae  mov     rdi, rcx
0x1800372b1  mov     [rax+18h], r14d
0x1800372b5  mov     [rax+20h], r14d
0x1800372b9  lea     ebp, [r14+1]
0x1800372bd  cmp     [r15], r14
0x1800372c0  jnz     short loc_1800372C9
0x1800372c2  mov     eax, [rcx+28h]
0x1800372c5  test    eax, eax
0x1800372c7  jz      short loc_1800372DA
0x1800372c9  mov     ecx, 8000FFFFh
0x1800372ce  mov     ebx, ecx
0x1800372d0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800372d5  jmp     loc_1800375E3
0x1800372da  cmp     [rcx+20h], r14
0x1800372de  jnz     short loc_1800372C9
0x1800372e0  mov     eax, [rcx+34h]
0x1800372e3  test    eax, eax
0x1800372e5  jnz     short loc_1800372C9
0x1800372e7  lea     r12, [rcx+48h]
0x1800372eb  cmp     [r12], r14
0x1800372ef  jnz     short loc_1800372C9
0x1800372f1  mov     [rsp+88h+ProcessAffinityMask], r14
0x1800372f9  mov     [rsp+88h+SystemAffinityMask], r14
0x180037301  call    cs:__imp_GetCurrentProcess
0x180037308  nop     dword ptr [rax+rax+00h]
0x18003730d  mov     rcx, rax; hProcess
0x180037310  lea     r8, [rsp+88h+SystemAffinityMask]; lpSystemAffinityMask
0x180037318  lea     rdx, [rsp+88h+ProcessAffinityMask]; lpProcessAffinityMask
0x180037320  call    cs:__imp_GetProcessAffinityMask
0x180037327  nop     dword ptr [rax+rax+00h]
0x18003732c  mov     esi, r14d
0x18003732f  test    eax, eax
0x180037331  jnz     short loc_180037360
0x180037333  call    cs:__imp_GetLastError
0x18003733a  nop     dword ptr [rax+rax+00h]
0x18003733f  mov     ebx, eax
0x180037341  test    eax, eax
0x180037343  jnz     short loc_18003734C
0x180037345  mov     ebx, 80004005h
0x18003734a  jmp     short loc_180037357
0x18003734c  jle     short loc_180037357
0x18003734e  movzx   ebx, ax
0x180037351  or      ebx, 80070000h
0x180037357  mov     ecx, ebx
0x180037359  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003735e  jmp     short loc_180037383
0x180037360  mov     rcx, [rsp+88h+ProcessAffinityMask]
0x180037368  mov     ebx, r14d
0x18003736b  test    rcx, rcx
0x18003736e  jz      short loc_180037383
0x180037370  lea     rax, [rcx-1]
0x180037374  add     esi, ebp
0x180037376  and     rcx, rax
0x180037379  jnz     short loc_180037370
0x18003737b  mov     [rsp+88h+ProcessAffinityMask], rcx
0x180037383  mov     ecx, ebx
0x180037385  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003738a  test    ebx, ebx
0x18003738c  jns     short loc_18003739A
0x18003738e  mov     ecx, ebx
0x180037390  mov     esi, r14d
0x180037393  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180037398  jmp     short loc_18003739F
0x18003739a  cmp     esi, ebp
0x18003739c  cmova   esi, ebp
0x18003739f  mov     ecx, ebx
0x1800373a1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800373a6  test    ebx, ebx
0x1800373a8  jns     short loc_1800373B1
0x1800373aa  mov     ecx, ebx
0x1800373ac  jmp     loc_1800372D0
0x1800373b1  call    cs:__imp_GetCurrentThread
0x1800373b8  nop     dword ptr [rax+rax+00h]
0x1800373bd  mov     rcx, rax; hThread
0x1800373c0  call    cs:__imp_GetThreadPriority
0x1800373c7  nop     dword ptr [rax+rax+00h]
0x1800373cc  mov     r13d, eax
0x1800373cf  cmp     eax, 7FFFFFFFh
0x1800373d4  jnz     short loc_180037406
0x1800373d6  mov     r13d, r14d
0x1800373d9  call    cs:__imp_GetLastError
0x1800373e0  nop     dword ptr [rax+rax+00h]
0x1800373e5  mov     ebx, eax
0x1800373e7  test    eax, eax
0x1800373e9  jnz     short loc_1800373F2
0x1800373eb  mov     ebx, 80004005h
0x1800373f0  jmp     short loc_1800373FD
0x1800373f2  jle     short loc_1800373FD
0x1800373f4  movzx   ebx, ax
0x1800373f7  or      ebx, 80070000h
0x1800373fd  mov     ecx, ebx
0x1800373ff  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180037404  jmp     short loc_180037409
0x180037406  mov     ebx, r14d
0x180037409  mov     ecx, ebx
0x18003740b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180037410  test    ebx, ebx
0x180037412  jns     short loc_18003741B
0x180037414  mov     ecx, ebx
0x180037416  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003741b  mov     ecx, ebx
0x18003741d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180037422  test    ebx, ebx
0x180037424  js      short loc_1800373AA
0x180037426  mov     eax, 40h ; '@'
0x18003742b  cmp     esi, eax
0x18003742d  cmovnb  esi, eax
0x180037430  xor     ecx, ecx; Ptr
0x180037432  call    cs:__imp_EncodePointer
0x180037439  nop     dword ptr [rax+rax+00h]
0x18003743e  mov     [rdi+40h], rax
0x180037442  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180037446  mov     rbx, [r12]
0x18003744a  test    rbx, rbx
0x18003744d  jz      short loc_180037492
0x18003744f  mov     eax, ecx
0x180037451  lock xadd [rbx], eax
0x180037455  add     eax, ecx
0x180037457  jnz     short loc_180037492
0x180037459  mov     rcx, [rbx+8]; hObject
0x18003745d  test    rcx, rcx
0x180037460  jz      short loc_180037472
0x180037462  call    cs:__imp_CloseHandle
0x180037469  nop     dword ptr [rax+rax+00h]
0x18003746e  mov     [rbx+8], r14
0x180037472  call    cs:__imp_GetProcessHeap
0x180037479  nop     dword ptr [rax+rax+00h]
0x18003747e  mov     r8, rbx; lpMem
0x180037481  xor     edx, edx; dwFlags
0x180037483  mov     rcx, rax; hHeap
0x180037486  call    cs:__imp_HeapFree
0x18003748d  nop     dword ptr [rax+rax+00h]
0x180037492  mov     [r12], r14
0x180037496  mov     [rdi+14h], r14d
0x18003749a  mov     [rdi+18h], r14d
0x18003749e  mov     [rdi+34h], ebp
0x1800374a1  mov     [rdi+38h], r14d
0x1800374a5  cmp     esi, 2
0x1800374a8  jb      short loc_180037518
0x1800374aa  xor     r9d, r9d; lpName
0x1800374ad  xor     edx, edx; lInitialCount
0x1800374af  xor     ecx, ecx; lpSemaphoreAttributes
0x1800374b1  mov     r8d, 7FFFFFFFh; lMaximumCount
0x1800374b7  call    cs:__imp_CreateSemaphoreW
0x1800374be  nop     dword ptr [rax+rax+00h]
0x1800374c3  mov     rcx, [rdi+20h]; hObject
0x1800374c7  mov     rbx, rax
0x1800374ca  test    rcx, rcx
0x1800374cd  jz      short loc_1800374DB
0x1800374cf  call    cs:__imp_CloseHandle
0x1800374d6  nop     dword ptr [rax+rax+00h]
0x1800374db  test    rbx, rbx
0x1800374de  jnz     short loc_180037514
0x1800374e0  mov     [rdi+20h], r14
0x1800374e4  call    cs:__imp_GetLastError
0x1800374eb  nop     dword ptr [rax+rax+00h]
0x1800374f0  mov     ebx, eax
0x1800374f2  test    eax, eax
0x1800374f4  jnz     short loc_180037500
0x1800374f6  mov     ebx, 80004005h
0x1800374fb  jmp     loc_1800373AA
0x180037500  jle     loc_1800373AA
0x180037506  movzx   ebx, ax
0x180037509  or      ebx, 80070000h
0x18003750f  jmp     loc_1800373AA
0x180037514  mov     [rdi+20h], rbx
0x180037518  mov     ebp, esi
0x18003751a  mov     eax, 8
0x18003751f  mul     rbp
0x180037522  mov     rbx, rax
0x180037525  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18003752c  cmovb   rbx, rax
0x180037530  add     rbx, 8
0x180037534  cmovb   rbx, rax
0x180037538  call    cs:__imp_GetProcessHeap
0x18003753f  nop     dword ptr [rax+rax+00h]
0x180037544  mov     r8, rbx; dwBytes
0x180037547  xor     edx, edx; dwFlags
0x180037549  mov     rcx, rax; hHeap
0x18003754c  call    cs:__imp_HeapAlloc
0x180037553  nop     dword ptr [rax+rax+00h]
0x180037558  test    rax, rax
0x18003755b  jz      loc_1800376AE
0x180037561  mov     [rax], rbp
0x180037564  lea     rbx, [rax+8]
0x180037568  mov     r14, rbx
0x18003756b  test    esi, esi
0x18003756d  jz      short loc_180037581
0x18003756f  mov     rcx, r14; this
0x180037572  call    ??0DH_HANDLE@@QEAA@XZ; DH_HANDLE::DH_HANDLE(void)
0x180037577  add     r14, 8
0x18003757b  sub     rbp, 1
0x18003757f  jnz     short loc_18003756F
0x180037581  xor     r14d, r14d
0x180037584  mov     [r15], rbx
0x180037587  test    rbx, rbx
0x18003758a  jz      loc_1800376B1
0x180037590  mov     ebx, r14d
0x180037593  mov     ebp, r14d
0x180037596  test    esi, esi
0x180037598  jz      short loc_1800375DE
0x18003759a  lock inc dword ptr [rdi]
0x18003759d  lock inc dword ptr [rdi+28h]
0x1800375a1  lock inc dword ptr [rdi+2Ch]
0x1800375a5  lock inc dword ptr [rdi+30h]
0x1800375a9  mov     rcx, [r15]
0x1800375ac  mov     r9, rdi; void *
0x1800375af  mov     eax, ebp
0x1800375b1  lea     rcx, [rcx+rax*8]; struct _SECURITY_ATTRIBUTES *
0x1800375b5  mov     [rsp+88h+var_50], rcx; void **
0x1800375ba  lea     rax, [rsp+88h+arg_18]
0x1800375c2  mov     [rsp+88h+var_58], rax; unsigned int *
0x1800375c7  mov     [rsp+88h+var_60], r13d; int
0x1800375cc  call    ?SafeThreadCreateEx@@YAJPEAU_SECURITY_ATTRIBUTES@@KP6AKPEAX@Z1KHPEAKPEAPEAX@Z; SafeThreadCreateEx(_SECURITY_ATTRIBUTES *,ulong,ulong (*)(void *),void *,ulong,int,ulong *,void * *)
0x1800375d1  mov     r14d, eax
0x1800375d4  test    eax, eax
0x1800375d6  js      short loc_18003763B
0x1800375d8  inc     ebp
0x1800375da  cmp     ebp, esi
0x1800375dc  jb      short loc_18003759A
0x1800375de  mov     ebp, 1
0x1800375e3  cmp     qword ptr [rdi+20h], 0
0x1800375e8  jz      short loc_18003760C
0x1800375ea  test    ebx, ebx
0x1800375ec  jns     short loc_1800375F1
0x1800375ee  mov     [rdi+18h], ebp
0x1800375f1  mov     edx, [rdi+2Ch]; lReleaseCount
0x1800375f4  lea     r8, [rsp+88h+PreviousCount]; lpPreviousCount
0x1800375fc  mov     rcx, [rdi+20h]; hSemaphore
0x180037600  call    cs:__imp_ReleaseSemaphore
0x180037607  nop     dword ptr [rax+rax+00h]
0x18003760c  test    ebx, ebx
0x18003760e  jns     short loc_180037620
0x180037610  mov     rcx, rdi
0x180037613  call    ?Wait@?$CAsyncOperationT@VCSmartCardDetector@CTokenActivation@@$00VCRefCountImpl@@$0A@@@AEAAJK@Z; CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::Wait(ulong)
0x180037618  mov     rcx, rdi
0x18003761b  call    ?Reset@?$CAsyncOperationT@VCSmartCardDetector@CTokenActivation@@$00VCRefCountImpl@@$0A@@@AEAAJXZ; CAsyncOperationT<CTokenActivation::CSmartCardDetector,1,CRefCountImpl,0>::Reset(void)
0x180037620  mov     ecx, ebx
0x180037622  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180037627  mov     eax, ebx
0x180037629  add     rsp, 48h
0x18003762d  pop     r15
0x18003762f  pop     r14
0x180037631  pop     r13
0x180037633  pop     r12
0x180037635  pop     rdi
0x180037636  pop     rsi
0x180037637  pop     rbp
0x180037638  pop     rbx
0x180037639  retn
0x18003763b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003763f  lock add [rdi+28h], ecx
0x180037643  lock add [rdi+2Ch], ecx
0x180037647  lock add [rdi+30h], ecx
0x18003764b  mov     eax, ecx
0x18003764d  lock xadd [rdi], eax
0x180037651  add     eax, ecx
0x180037653  jnz     short loc_18003769E
0x180037655  mov     rcx, r12
0x180037658  call    ??1?$SP@V?$CRefCountWrapper@VDH_HANDLE@@@@V?$SP_COM@V?$CRefCountWrapper@VDH_HANDLE@@@@@@@@QEAA@XZ; SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>::~SP<CRefCountWrapper<DH_HANDLE>,SP_COM<CRefCountWrapper<DH_HANDLE>>>(void)
0x18003765d  mov     rcx, [rdi+20h]; hObject
0x180037661  test    rcx, rcx
0x180037664  jz      short loc_180037676
0x180037666  call    cs:__imp_CloseHandle
0x18003766d  nop     dword ptr [rax+rax+00h]
0x180037672  mov     [rdi+20h], rbx
0x180037676  mov     rcx, r15
0x180037679  call    ??1?$SP@VDH_HANDLE@@V?$SP_CPP_ARRAY@VDH_HANDLE@@@@@@QEAA@XZ; SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>::~SP<DH_HANDLE,SP_CPP_ARRAY<DH_HANDLE>>(void)
0x18003767e  call    cs:__imp_GetProcessHeap
0x180037685  nop     dword ptr [rax+rax+00h]
0x18003768a  mov     r8, rdi; lpMem
0x18003768d  xor     edx, edx; dwFlags
0x18003768f  mov     rcx, rax; hHeap
0x180037692  call    cs:__imp_HeapFree
0x180037699  nop     dword ptr [rax+rax+00h]
0x18003769e  mov     ebx, r14d
0x1800376a1  mov     ecx, r14d
0x1800376a4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800376a9  jmp     loc_1800375DE
0x1800376ae  mov     [r15], r14
0x1800376b1  mov     ebx, 8007000Eh
0x1800376b6  mov     ecx, ebx
0x1800376b8  jmp     short loc_1800376A4
```

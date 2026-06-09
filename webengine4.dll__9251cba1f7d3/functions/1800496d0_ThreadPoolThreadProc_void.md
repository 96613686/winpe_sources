# ThreadPoolThreadProc(void *)

- ea: `0x1800496d0`
- end: `0x1800497cf`
- name: `?ThreadPoolThreadProc@@YAKPEAX@Z`
- size: `255`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180048fd8`
- `0x1800492e4`
- `0x1800496d0`
- `0x18004d350`
- `0x180065b60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180049743`
- `KERNEL32!GetLastError` at `0x180049743`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180049732`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180049732`
- `ole32!CoUninitialize` at `0x1800497ba`
- `ole32!CoUninitialize` at `0x1800497ba`
- `ole32!CoInitializeEx` at `0x1800496da`
- `ole32!CoInitializeEx` at `0x1800496da`

## pseudocode

```c
__int64 __fastcall ThreadPoolThreadProc(void *a1)
{
  unsigned int LastWin32Error; // ebx
  BOOL QueuedCompletionStatus; // eax
  unsigned __int64 Internal; // rcx
  DWORD NumberOfBytesTransferred; // [rsp+48h] [rbp+10h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+50h] [rbp+18h] BYREF
  unsigned __int64 CompletionKey; // [rsp+58h] [rbp+20h] BYREF

  CoInitializeEx(0, 0);
  while ( THREADPOOL::g_NumFreeThreads <= THREADPOOL::g_MaxFreeThreads
       && THREADPOOL::g_NumThreads <= THREADPOOL::g_NumThreadsLimit
       || !IsCurrentThreadExitable() )
  {
    _InterlockedIncrement(&THREADPOOL::g_NumFreeThreads);
    LastWin32Error = 0;
    QueuedCompletionStatus = GetQueuedCompletionStatus(
                               THREADPOOL::g_CompletionPort,
                               &NumberOfBytesTransferred,
                               &CompletionKey,
                               &Overlapped,
                               THREADPOOL::g_ThreadWaitMsec);
    _InterlockedDecrement(&THREADPOOL::g_NumFreeThreads);
    if ( !QueuedCompletionStatus )
    {
      if ( GetLastError() == 258 )
        continue;
      LastWin32Error = GetLastWin32Error();
      if ( LastWin32Error == -2147024638 )
        continue;
    }
    if ( !CompletionKey && !Overlapped )
      break;
    if ( (_WORD)LastWin32Error != 995 || !g_fShuttingDown )
    {
      GrowThreadPoolIfNeeded();
      Internal = CompletionKey;
      if ( !CompletionKey )
        Internal = Overlapped[1].Internal;
      (*(void (__fastcall **)(unsigned __int64, _QWORD, _QWORD, LPOVERLAPPED))(*(_QWORD *)Internal + 24LL))(
        Internal,
        LastWin32Error,
        NumberOfBytesTransferred,
        Overlapped);
      _InterlockedDecrement(&THREADPOOL::g_NumCurrentCalls);
    }
  }
  CoUninitialize();
  _InterlockedDecrement(&THREADPOOL::g_NumThreads);
  return 0;
}

```

## disassembly

```asm
0x1800496d0  push    rbx
0x1800496d2  sub     rsp, 30h
0x1800496d6  xor     edx, edx; dwCoInit
0x1800496d8  xor     ecx, ecx; pvReserved
0x1800496da  call    cs:__imp_CoInitializeEx
0x1800496e0  mov     eax, cs:?g_MaxFreeThreads@THREADPOOL@@3JA; long THREADPOOL::g_MaxFreeThreads
0x1800496e6  cmp     cs:?g_NumFreeThreads@THREADPOOL@@3JA, eax; long THREADPOOL::g_NumFreeThreads
0x1800496ec  jg      short loc_1800496FC
0x1800496ee  mov     eax, cs:?g_NumThreadsLimit@THREADPOOL@@3JA; long THREADPOOL::g_NumThreadsLimit
0x1800496f4  cmp     cs:?g_NumThreads@THREADPOOL@@3JA, eax; long THREADPOOL::g_NumThreads
0x1800496fa  jle     short loc_180049709
0x1800496fc  call    ?IsCurrentThreadExitable@@YAHXZ; IsCurrentThreadExitable(void)
0x180049701  test    eax, eax
0x180049703  jnz     loc_1800497BA
0x180049709  lock inc cs:?g_NumFreeThreads@THREADPOOL@@3JA; long THREADPOOL::g_NumFreeThreads
0x180049710  mov     eax, cs:?g_ThreadWaitMsec@THREADPOOL@@3JA; long THREADPOOL::g_ThreadWaitMsec
0x180049716  lea     r9, [rsp+38h+Overlapped]; lpOverlapped
0x18004971b  mov     rcx, cs:?g_CompletionPort@THREADPOOL@@3PEAXEA; CompletionPort
0x180049722  lea     r8, [rsp+38h+CompletionKey]; lpCompletionKey
0x180049727  lea     rdx, [rsp+38h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18004972c  mov     [rsp+38h+dwMilliseconds], eax; dwMilliseconds
0x180049730  xor     ebx, ebx
0x180049732  call    cs:__imp_GetQueuedCompletionStatus
0x180049738  lock dec cs:?g_NumFreeThreads@THREADPOOL@@3JA; long THREADPOOL::g_NumFreeThreads
0x18004973f  test    eax, eax
0x180049741  jnz     short loc_18004975E
0x180049743  call    cs:__imp_GetLastError
0x180049749  cmp     eax, 102h
0x18004974e  jz      short loc_1800496E0
0x180049750  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180049755  mov     ebx, eax
0x180049757  cmp     eax, 80070102h
0x18004975c  jz      short loc_1800496E0
0x18004975e  cmp     [rsp+38h+CompletionKey], 0
0x180049764  jnz     short loc_18004976E
0x180049766  cmp     [rsp+38h+Overlapped], 0
0x18004976c  jz      short loc_1800497BA
0x18004976e  cmp     bx, 3E3h
0x180049773  jnz     short loc_180049782
0x180049775  cmp     cs:?g_fShuttingDown@@3HA, 0; int g_fShuttingDown
0x18004977c  jnz     loc_1800496E0
0x180049782  call    ?GrowThreadPoolIfNeeded@@YAXXZ; GrowThreadPoolIfNeeded(void)
0x180049787  mov     rcx, [rsp+38h+CompletionKey]
0x18004978c  mov     r9, [rsp+38h+Overlapped]
0x180049791  test    rcx, rcx
0x180049794  jnz     short loc_18004979A
0x180049796  mov     rcx, [r9+20h]
0x18004979a  mov     rax, [rcx]
0x18004979d  mov     edx, ebx
0x18004979f  mov     r8d, [rsp+38h+NumberOfBytesTransferred]
0x1800497a4  mov     rax, [rax+18h]
0x1800497a8  call    cs:__guard_dispatch_icall_fptr
0x1800497ae  lock dec cs:?g_NumCurrentCalls@THREADPOOL@@3JA; long THREADPOOL::g_NumCurrentCalls
0x1800497b5  jmp     loc_1800496E0
0x1800497ba  call    cs:__imp_CoUninitialize
0x1800497c0  lock dec cs:?g_NumThreads@THREADPOOL@@3JA; long THREADPOOL::g_NumThreads
0x1800497c7  xor     eax, eax
0x1800497c9  add     rsp, 30h
0x1800497cd  pop     rbx
0x1800497ce  retn
```

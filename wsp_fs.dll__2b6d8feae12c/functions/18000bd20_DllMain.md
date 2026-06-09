# DllMain

- ea: `0x18000bd20`
- end: `0x18000bdd9`
- name: `DllMain`
- size: `185`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800028d4`

## callees

- `0x1800011c4`
- `0x180001274`
- `0x18000bd20`
- `0x180019254`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bd66`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bd66`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000bd3b`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000bd3b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bda0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bdc8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bda0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bdc8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18000bdb4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x18000bdb4`
- `sscore!SsCoreUninitialize` at `0x18000bd93`
- `sscore!SsCoreUninitialize` at `0x18000bd93`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
  {
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(hinstDLL, fdwReason, lpvReserved);
    ClRtlInitializeEx();
    DisableThreadLibraryCalls(hinstDLL);
    g_hModule = (__int64)hinstDLL;
  }
  else if ( !fdwReason )
  {
    if ( g_hHelper )
      FreeLibrary(g_hHelper);
    TraceLoggingUnregister_EventUnregister(hinstDLL, *(_QWORD *)&fdwReason, lpvReserved);
    if ( ClRtlpInitialized )
    {
      ClRtlpInitialized = 0;
      if ( !ClRtlSsCoreInitStatus )
      {
        ClRtlSsCoreInitStatus = -2147467259;
        SsCoreUninitialize();
      }
      DeleteCriticalSection(&EventLogLock);
      if ( ClRtlWatchdogTimerQueue )
      {
        DeleteTimerQueueEx(ClRtlWatchdogTimerQueue, 0);
        ClRtlWatchdogTimerQueue = 0;
      }
      DeleteCriticalSection(&ShareConnectSDLock);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000bd20  push    rbx
0x18000bd22  sub     rsp, 20h
0x18000bd26  mov     rbx, rcx
0x18000bd29  cmp     edx, 1
0x18000bd2c  jnz     short loc_18000BD4D
0x18000bd2e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000bd33  call    ClRtlInitializeEx
0x18000bd38  mov     rcx, rbx; hLibModule
0x18000bd3b  call    cs:__imp_DisableThreadLibraryCalls
0x18000bd41  mov     cs:g_hModule, rbx
0x18000bd48  jmp     loc_18000BDCE
0x18000bd4d  xor     ebx, ebx
0x18000bd4f  test    edx, edx
0x18000bd51  jnz     short loc_18000BDCE
0x18000bd53  mov     rax, cs:g_hHelper
0x18000bd5a  test    rax, rax
0x18000bd5d  jz      short loc_18000BD6C
0x18000bd5f  mov     rcx, cs:g_hHelper; hLibModule
0x18000bd66  call    cs:__imp_FreeLibrary
0x18000bd6c  call    TraceLoggingUnregister_EventUnregister
0x18000bd71  cmp     cs:?ClRtlpInitialized@@3HA, ebx; int ClRtlpInitialized
0x18000bd77  jz      short loc_18000BDCE
0x18000bd79  mov     eax, cs:?ClRtlSsCoreInitStatus@@3KC; ulong volatile ClRtlSsCoreInitStatus
0x18000bd7f  mov     cs:?ClRtlpInitialized@@3HA, ebx; int ClRtlpInitialized
0x18000bd85  test    eax, eax
0x18000bd87  jnz     short loc_18000BD99
0x18000bd89  mov     cs:?ClRtlSsCoreInitStatus@@3KC, 80004005h; ulong volatile ClRtlSsCoreInitStatus
0x18000bd93  call    cs:__imp_SsCoreUninitialize
0x18000bd99  lea     rcx, EventLogLock; lpCriticalSection
0x18000bda0  call    cs:__imp_DeleteCriticalSection
0x18000bda6  mov     rcx, cs:?ClRtlWatchdogTimerQueue@@3PEAXEA; TimerQueue
0x18000bdad  test    rcx, rcx
0x18000bdb0  jz      short loc_18000BDC1
0x18000bdb2  xor     edx, edx; CompletionEvent
0x18000bdb4  call    cs:__imp_DeleteTimerQueueEx
0x18000bdba  mov     cs:?ClRtlWatchdogTimerQueue@@3PEAXEA, rbx; void * ClRtlWatchdogTimerQueue
0x18000bdc1  lea     rcx, ?ShareConnectSDLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000bdc8  call    cs:__imp_DeleteCriticalSection
0x18000bdce  mov     eax, 1
0x18000bdd3  add     rsp, 20h
0x18000bdd7  pop     rbx
0x18000bdd8  retn
```

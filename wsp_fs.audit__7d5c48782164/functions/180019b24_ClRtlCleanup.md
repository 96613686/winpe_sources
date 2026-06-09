# ClRtlCleanup

- ea: `0x180019b24`
- end: `0x180019bac`
- name: `ClRtlCleanup`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c060`

## callees

- `0x180019b24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019b62`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019b9a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019b62`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019b9a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180019b7c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180019b7c`
- `sscore!SsCoreUninitialize` at `0x180019b4f`
- `sscore!SsCoreUninitialize` at `0x180019b4f`

## pseudocode

```c
void ClRtlCleanup()
{
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

```

## disassembly

```asm
0x180019b24  sub     rsp, 28h
0x180019b28  cmp     cs:?ClRtlpInitialized@@3HA, 0; int ClRtlpInitialized
0x180019b2f  jz      short loc_180019BA6
0x180019b31  mov     eax, cs:?ClRtlSsCoreInitStatus@@3KC; ulong volatile ClRtlSsCoreInitStatus
0x180019b37  mov     cs:?ClRtlpInitialized@@3HA, 0; int ClRtlpInitialized
0x180019b41  test    eax, eax
0x180019b43  jnz     short loc_180019B5B
0x180019b45  mov     cs:?ClRtlSsCoreInitStatus@@3KC, 80004005h; ulong volatile ClRtlSsCoreInitStatus
0x180019b4f  call    cs:__imp_SsCoreUninitialize
0x180019b56  nop     dword ptr [rax+rax+00h]
0x180019b5b  lea     rcx, EventLogLock; lpCriticalSection
0x180019b62  call    cs:__imp_DeleteCriticalSection
0x180019b69  nop     dword ptr [rax+rax+00h]
0x180019b6e  mov     rcx, cs:?ClRtlWatchdogTimerQueue@@3PEAXEA; TimerQueue
0x180019b75  test    rcx, rcx
0x180019b78  jz      short loc_180019B93
0x180019b7a  xor     edx, edx; CompletionEvent
0x180019b7c  call    cs:__imp_DeleteTimerQueueEx
0x180019b83  nop     dword ptr [rax+rax+00h]
0x180019b88  mov     cs:?ClRtlWatchdogTimerQueue@@3PEAXEA, 0; void * ClRtlWatchdogTimerQueue
0x180019b93  lea     rcx, ?ShareConnectSDLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019b9a  call    cs:__imp_DeleteCriticalSection
0x180019ba1  nop     dword ptr [rax+rax+00h]
0x180019ba6  add     rsp, 28h
0x180019baa  retn
```

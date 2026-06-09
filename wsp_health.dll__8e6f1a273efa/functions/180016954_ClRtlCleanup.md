# ClRtlCleanup

- ea: `0x180016954`
- end: `0x1800169dc`
- name: `ClRtlCleanup`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b790`

## callees

- `0x180016954`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016992`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800169ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016992`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800169ca`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800169ac`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800169ac`
- `sscore!SsCoreUninitialize` at `0x18001697f`
- `sscore!SsCoreUninitialize` at `0x18001697f`

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
0x180016954  sub     rsp, 28h
0x180016958  cmp     cs:?ClRtlpInitialized@@3HA, 0; int ClRtlpInitialized
0x18001695f  jz      short loc_1800169D6
0x180016961  mov     eax, cs:?ClRtlSsCoreInitStatus@@3KC; ulong volatile ClRtlSsCoreInitStatus
0x180016967  mov     cs:?ClRtlpInitialized@@3HA, 0; int ClRtlpInitialized
0x180016971  test    eax, eax
0x180016973  jnz     short loc_18001698B
0x180016975  mov     cs:?ClRtlSsCoreInitStatus@@3KC, 80004005h; ulong volatile ClRtlSsCoreInitStatus
0x18001697f  call    cs:__imp_SsCoreUninitialize
0x180016986  nop     dword ptr [rax+rax+00h]
0x18001698b  lea     rcx, EventLogLock; lpCriticalSection
0x180016992  call    cs:__imp_DeleteCriticalSection
0x180016999  nop     dword ptr [rax+rax+00h]
0x18001699e  mov     rcx, cs:?ClRtlWatchdogTimerQueue@@3PEAXEA; TimerQueue
0x1800169a5  test    rcx, rcx
0x1800169a8  jz      short loc_1800169C3
0x1800169aa  xor     edx, edx; CompletionEvent
0x1800169ac  call    cs:__imp_DeleteTimerQueueEx
0x1800169b3  nop     dword ptr [rax+rax+00h]
0x1800169b8  mov     cs:?ClRtlWatchdogTimerQueue@@3PEAXEA, 0; void * ClRtlWatchdogTimerQueue
0x1800169c3  lea     rcx, ?ShareConnectSDLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800169ca  call    cs:__imp_DeleteCriticalSection
0x1800169d1  nop     dword ptr [rax+rax+00h]
0x1800169d6  add     rsp, 28h
0x1800169da  retn
```

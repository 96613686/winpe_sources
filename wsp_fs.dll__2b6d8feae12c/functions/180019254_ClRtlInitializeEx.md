# ClRtlInitializeEx

- ea: `0x180019254`
- end: `0x18001929f`
- name: `ClRtlInitializeEx`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000bd20`

## callees

- `0x180019254`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180019268`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180019285`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180019268`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180019285`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019278`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019278`
- `api-ms-win-core-synch-l1-2-0!InitOnceInitialize` at `0x180019292`
- `api-ms-win-core-synch-l1-2-0!InitOnceInitialize` at `0x180019292`

## pseudocode

```c
__int64 ClRtlInitializeEx()
{
  if ( !ClRtlpInitialized )
  {
    InitializeCriticalSection(&EventLogLock);
    ClRtlpInitialized = 1;
    GetCurrentProcessId();
    InitializeCriticalSection(&ShareConnectSDLock);
    InitOnceInitialize(&ClRtlSsCoreInitOnce);
  }
  return 0;
}

```

## disassembly

```asm
0x180019254  sub     rsp, 28h
0x180019258  cmp     cs:?ClRtlpInitialized@@3HA, 0; int ClRtlpInitialized
0x18001925f  jnz     short loc_180019298
0x180019261  lea     rcx, EventLogLock; lpCriticalSection
0x180019268  call    cs:__imp_InitializeCriticalSection
0x18001926e  mov     cs:?ClRtlpInitialized@@3HA, 1; int ClRtlpInitialized
0x180019278  call    cs:__imp_GetCurrentProcessId
0x18001927e  lea     rcx, ?ShareConnectSDLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019285  call    cs:__imp_InitializeCriticalSection
0x18001928b  lea     rcx, ?ClRtlSsCoreInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180019292  call    cs:__imp_InitOnceInitialize
0x180019298  xor     eax, eax
0x18001929a  add     rsp, 28h
0x18001929e  retn
```

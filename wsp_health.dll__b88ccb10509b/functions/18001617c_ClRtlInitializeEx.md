# ClRtlInitializeEx

- ea: `0x18001617c`
- end: `0x1800161c7`
- name: `ClRtlInitializeEx`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000b410`

## callees

- `0x18001617c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180016190`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800161ad`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180016190`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800161ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800161a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800161a0`
- `api-ms-win-core-synch-l1-2-0!InitOnceInitialize` at `0x1800161ba`
- `api-ms-win-core-synch-l1-2-0!InitOnceInitialize` at `0x1800161ba`

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
0x18001617c  sub     rsp, 28h
0x180016180  cmp     cs:?ClRtlpInitialized@@3HA, 0; int ClRtlpInitialized
0x180016187  jnz     short loc_1800161C0
0x180016189  lea     rcx, EventLogLock; lpCriticalSection
0x180016190  call    cs:__imp_InitializeCriticalSection
0x180016196  mov     cs:?ClRtlpInitialized@@3HA, 1; int ClRtlpInitialized
0x1800161a0  call    cs:__imp_GetCurrentProcessId
0x1800161a6  lea     rcx, ?ShareConnectSDLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800161ad  call    cs:__imp_InitializeCriticalSection
0x1800161b3  lea     rcx, ?ClRtlSsCoreInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800161ba  call    cs:__imp_InitOnceInitialize
0x1800161c0  xor     eax, eax
0x1800161c2  add     rsp, 28h
0x1800161c6  retn
```

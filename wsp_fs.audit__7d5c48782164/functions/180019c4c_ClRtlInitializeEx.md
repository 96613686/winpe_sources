# ClRtlInitializeEx

- ea: `0x180019c4c`
- end: `0x180019cb0`
- name: `ClRtlInitializeEx`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000c060`

## callees

- `0x180019c4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180019c60`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180019c89`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180019c60`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180019c89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019c76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019c76`
- `api-ms-win-core-synch-l1-2-0!InitOnceInitialize` at `0x180019c9c`
- `api-ms-win-core-synch-l1-2-0!InitOnceInitialize` at `0x180019c9c`

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
0x180019c4c  sub     rsp, 28h
0x180019c50  cmp     cs:?ClRtlpInitialized@@3HA, 0; int ClRtlpInitialized
0x180019c57  jnz     short loc_180019CA8
0x180019c59  lea     rcx, EventLogLock; lpCriticalSection
0x180019c60  call    cs:__imp_InitializeCriticalSection
0x180019c67  nop     dword ptr [rax+rax+00h]
0x180019c6c  mov     cs:?ClRtlpInitialized@@3HA, 1; int ClRtlpInitialized
0x180019c76  call    cs:__imp_GetCurrentProcessId
0x180019c7d  nop     dword ptr [rax+rax+00h]
0x180019c82  lea     rcx, ?ShareConnectSDLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180019c89  call    cs:__imp_InitializeCriticalSection
0x180019c90  nop     dword ptr [rax+rax+00h]
0x180019c95  lea     rcx, ?ClRtlSsCoreInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180019c9c  call    cs:__imp_InitOnceInitialize
0x180019ca3  nop     dword ptr [rax+rax+00h]
0x180019ca8  xor     eax, eax
0x180019caa  add     rsp, 28h
0x180019cae  retn
```

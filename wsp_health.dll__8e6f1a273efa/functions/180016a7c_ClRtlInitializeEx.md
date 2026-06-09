# ClRtlInitializeEx

- ea: `0x180016a7c`
- end: `0x180016ae0`
- name: `ClRtlInitializeEx`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000b790`

## callees

- `0x180016a7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180016a90`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180016ab9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180016a90`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180016ab9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016aa6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016aa6`
- `api-ms-win-core-synch-l1-2-0!InitOnceInitialize` at `0x180016acc`
- `api-ms-win-core-synch-l1-2-0!InitOnceInitialize` at `0x180016acc`

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
0x180016a7c  sub     rsp, 28h
0x180016a80  cmp     cs:?ClRtlpInitialized@@3HA, 0; int ClRtlpInitialized
0x180016a87  jnz     short loc_180016AD8
0x180016a89  lea     rcx, EventLogLock; lpCriticalSection
0x180016a90  call    cs:__imp_InitializeCriticalSection
0x180016a97  nop     dword ptr [rax+rax+00h]
0x180016a9c  mov     cs:?ClRtlpInitialized@@3HA, 1; int ClRtlpInitialized
0x180016aa6  call    cs:__imp_GetCurrentProcessId
0x180016aad  nop     dword ptr [rax+rax+00h]
0x180016ab2  lea     rcx, ?ShareConnectSDLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180016ab9  call    cs:__imp_InitializeCriticalSection
0x180016ac0  nop     dword ptr [rax+rax+00h]
0x180016ac5  lea     rcx, ?ClRtlSsCoreInitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x180016acc  call    cs:__imp_InitOnceInitialize
0x180016ad3  nop     dword ptr [rax+rax+00h]
0x180016ad8  xor     eax, eax
0x180016ada  add     rsp, 28h
0x180016ade  retn
```

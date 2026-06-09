# CTSTimerManager::TimerThread(void)

- ea: `0x180025250`
- end: `0x180025460`
- name: `?TimerThread@CTSTimerManager@@QEAAKXZ`
- size: `528`
- prototype: `unsigned int __fastcall(CTSTimerManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18006cda0`

## callees

- `0x18000a210`
- `0x180013150`
- `0x1800241f0`
- `0x180025250`
- `0x180025468`
- `0x1800c8010`

## import_xrefs

- `ntdll!NtQuerySystemTime` at `0x18002531c`
- `ntdll!NtQuerySystemTime` at `0x18002531c`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800252e5`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800252e5`
- `ntdll!RtlReleaseResource` at `0x180025304`
- `ntdll!RtlReleaseResource` at `0x180025392`
- `ntdll!RtlReleaseResource` at `0x1800253d7`
- `ntdll!RtlReleaseResource` at `0x180025304`
- `ntdll!RtlReleaseResource` at `0x180025392`
- `ntdll!RtlReleaseResource` at `0x1800253d7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180025378`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180025378`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800252c0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800253a6`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800252c0`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800253a6`

## string_xrefs

- `0x18002542e`: `Ending execution of Timer Thread`

## pseudocode

```c

```

# PfXpRefreshIdleTasks

- ea: `0x180058b30`
- end: `0x180058c23`
- name: `PfXpRefreshIdleTasks`
- size: `243`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180065770`

## callees

- `0x180055800`
- `0x180055970`
- `0x180058b30`
- `0x180058c2c`
- `0x180058c88`
- `0x180071874`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058b4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058bfd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058b4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058bfd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058b6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058b6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058c1c`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180058b7d`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180058b7d`

## pseudocode

```c

```

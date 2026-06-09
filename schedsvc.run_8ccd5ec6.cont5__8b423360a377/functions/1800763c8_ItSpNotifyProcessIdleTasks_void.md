# ItSpNotifyProcessIdleTasks(void)

- ea: `0x1800763c8`
- end: `0x18007655b`
- name: `?ItSpNotifyProcessIdleTasks@@YAXXZ`
- size: `403`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x180077f90`

## callees

- `0x1800403a4`
- `0x18005599c`
- `0x1800763c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007645d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007653e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007645d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007653e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800763e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076498`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800763e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180076498`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18007642d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800764ac`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18007642d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800764ac`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180076483`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180076483`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007643d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007643d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180076518`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180076518`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076504`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076504`

## pseudocode

```c

```

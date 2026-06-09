# Scheduler::EnqueueExpiredTaskDeletion(JobMoniker const &,TSTime const &)

- ea: `0x18006c210`
- end: `0x18006c373`
- name: `?EnqueueExpiredTaskDeletion@Scheduler@@QEAAJAEBVJobMoniker@@AEBVTSTime@@@Z`
- size: `355`
- prototype: `int(Scheduler *__hidden this, const struct JobMoniker *, const struct TSTime *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18007485c`

## callees

- `0x180009d90`
- `0x180016590`
- `0x1800514b0`
- `0x18006c0c8`
- `0x18006c210`
- `0x18006cefc`
- `0x180082a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c2f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c341`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c2f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006c341`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c2cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c2cd`

## pseudocode

```c

```

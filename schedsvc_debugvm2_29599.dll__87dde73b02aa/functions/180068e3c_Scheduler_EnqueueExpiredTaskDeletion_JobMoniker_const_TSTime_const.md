# Scheduler::EnqueueExpiredTaskDeletion(JobMoniker const &,TSTime const &)

- ea: `0x180068e3c`
- end: `0x180068f8c`
- name: `?EnqueueExpiredTaskDeletion@Scheduler@@QEAAJAEBVJobMoniker@@AEBVTSTime@@@Z`
- size: `336`
- prototype: `int(Scheduler *__hidden this, const struct JobMoniker *, const struct TSTime *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180070f0c`

## callees

- `0x1800150b0`
- `0x180031c00`
- `0x18005013c`
- `0x180068cf8`
- `0x180068e3c`
- `0x180069ad4`
- `0x18007e6d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068f1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068f61`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068f1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068f61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068ef9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068ef9`

## pseudocode

```c

```

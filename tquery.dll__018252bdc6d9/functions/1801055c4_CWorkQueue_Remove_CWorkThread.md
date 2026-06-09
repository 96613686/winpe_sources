# CWorkQueue::Remove(CWorkThread &)

- ea: `0x1801055c4`
- end: `0x1801057c5`
- name: `?Remove@CWorkQueue@@AEAAXAEAVCWorkThread@@@Z`
- size: `513`
- prototype: `void(CWorkQueue *__hidden this, struct CWorkThread *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180105520`

## callees

- `0x180068b14`
- `0x180072768`
- `0x180074fac`
- `0x1800eb364`
- `0x1800eb3b0`
- `0x1801055c4`
- `0x1801aa134`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801055f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801055f8`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x1801057be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180105680`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180105763`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180105680`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180105763`

## string_xrefs

- `0x180105779`: `[Query] Work queue: remove 0x%x\n`
- `0x180105737`: `[Query] Work queue: abort worker thread.\n`

## pseudocode

```c

```

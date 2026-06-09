# CTSTimerManager::Stop(void)

- ea: `0x18006cc8c`
- end: `0x18006cd93`
- name: `?Stop@CTSTimerManager@@QEAAJXZ`
- size: `263`
- prototype: `__int64 __fastcall(CTSTimerManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18006c94c`
- `0x180070dfc`

## callees

- `0x18000a210`
- `0x180013150`
- `0x1800241f0`
- `0x180025468`
- `0x18006cc8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006cce5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18006cce5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006ccce`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006ccce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ccf2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ccf2`

## string_xrefs

- `0x18006cd4e`: `Could not remove a timer when stopping timer manager`

## pseudocode

```c

```

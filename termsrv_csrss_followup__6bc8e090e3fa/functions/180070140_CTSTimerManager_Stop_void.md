# CTSTimerManager::Stop(void)

- ea: `0x180070140`
- end: `0x18007025a`
- name: `?Stop@CTSTimerManager@@QEAAJXZ`
- size: `282`
- prototype: `__int64 __fastcall(CTSTimerManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18006fdf0`
- `0x180074320`

## callees

- `0x180009940`
- `0x1800139c0`
- `0x18002558c`
- `0x18002684c`
- `0x180070140`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007019f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007019f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180070182`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180070182`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800701b2`

## string_xrefs

- `0x180070214`: `Could not remove a timer when stopping timer manager`

## pseudocode

```c

```

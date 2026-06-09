# WctSyscallCalibratorThreadProc

- ea: `0x180061710`
- end: `0x180061804`
- name: `WctSyscallCalibratorThreadProc`
- size: `244`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180004c64`
- `0x180020680`
- `0x180061710`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x180061781`
- `ntdll!NtWaitForSingleObject` at `0x180061781`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061793`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180061793`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800617b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800617b6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800617a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800617a6`

## pseudocode

```c

```

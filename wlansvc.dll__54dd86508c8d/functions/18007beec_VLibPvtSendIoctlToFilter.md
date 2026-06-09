# VLibPvtSendIoctlToFilter

- ea: `0x18007beec`
- end: `0x18007c09f`
- name: `VLibPvtSendIoctlToFilter`
- size: `435`
- prototype: `__int64 __fastcall(DWORD dwIoControlCode, LPVOID lpInBuffer, DWORD nInBufferSize, LPVOID lpOutBuffer, DWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180052424`
- `0x18007bdb4`
- `0x180092170`
- `0x180094b18`
- `0x1801d5bb0`
- `0x1801d5da4`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x18007beec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18007bf35`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18007bf35`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007bf92`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18007bf92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c053`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c08d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007c08d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007bf7c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007bf7c`

## pseudocode

```c

```

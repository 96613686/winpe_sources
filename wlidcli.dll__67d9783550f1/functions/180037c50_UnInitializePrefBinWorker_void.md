# UnInitializePrefBinWorker(void)

- ea: `0x180037c50`
- end: `0x180037da1`
- name: `?UnInitializePrefBinWorker@@YAXXZ`
- size: `337`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180019db0`

## callees

- `0x18000e870`
- `0x18000e9a4`
- `0x180037c50`
- `0x1800530e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037ca8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180037ca8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180037c8e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180037c8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037cef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037cef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037ce5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037d3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037d57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037d74`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037ce5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037d3a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037d57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037d74`

## string_xrefs

- `0x180037cbc`: `Nonblocking Failure: WaitForSingleObject(g_hPrefBinThread, 5000) failed with hr=0x%x`
- `0x180037d01`: `Nonblocking Failure: CloseHandle(g_hPrefBinThread) failed with hr=0x%x`

## pseudocode

```c

```

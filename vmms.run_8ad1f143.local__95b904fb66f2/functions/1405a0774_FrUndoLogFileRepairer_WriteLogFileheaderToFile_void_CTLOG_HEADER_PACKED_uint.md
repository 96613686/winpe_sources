# FrUndoLogFileRepairer::WriteLogFileheaderToFile(void *,_CTLOG_HEADER_PACKED *,uint)

- ea: `0x1405a0774`
- end: `0x1405a0a28`
- name: `?WriteLogFileheaderToFile@FrUndoLogFileRepairer@@SAJPEAXPEAU_CTLOG_HEADER_PACKED@@I@Z`
- size: `692`
- prototype: `__int64 __fastcall(HANDLE hFile, LPCVOID lpBuffer, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x14059d378`

## callees

- `0x14005c630`
- `0x1401879a4`
- `0x1404828e0`
- `0x1405a0774`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1405a07d4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1405a07d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1405a08da`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1405a08da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405a0837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405a087c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405a08ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405a08eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405a094a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405a097d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405a09c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405a0837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405a087c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405a08ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405a08eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405a094a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405a097d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1405a09c7`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1405a09b7`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1405a09b7`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1405a07fc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1405a07fc`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1405a0827`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1405a0936`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1405a0827`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1405a0936`

## pseudocode

```c

```

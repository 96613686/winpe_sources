# W3_MGD_HANDLER::WriteEntityChunkAfterCopy(_HTTP_DATA_CHUNK *)

- ea: `0x180062d4c`
- end: `0x180062eec`
- name: `?WriteEntityChunkAfterCopy@W3_MGD_HANDLER@@AEAAJPEAU_HTTP_DATA_CHUNK@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(W3_MGD_HANDLER *__hidden this, struct _HTTP_DATA_CHUNK *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800624fc`

## callees

- `0x1800602a4`
- `0x180060318`
- `0x180062d4c`
- `0x1800653ba`
- `0x180065b60`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180062e2a`
- `KERNEL32!CloseHandle` at `0x180062e2a`
- `KERNEL32!GetLastError` at `0x180062dfa`
- `KERNEL32!GetLastError` at `0x180062dfa`
- `KERNEL32!GetCurrentProcess` at `0x180062dc1`
- `KERNEL32!GetCurrentProcess` at `0x180062dca`
- `KERNEL32!GetCurrentProcess` at `0x180062dc1`
- `KERNEL32!GetCurrentProcess` at `0x180062dca`
- `KERNEL32!HeapAlloc` at `0x180062e66`
- `KERNEL32!HeapAlloc` at `0x180062e66`
- `KERNEL32!HeapFree` at `0x180062e9c`
- `KERNEL32!HeapFree` at `0x180062e9c`
- `KERNEL32!DuplicateHandle` at `0x180062df0`
- `KERNEL32!DuplicateHandle` at `0x180062df0`
- `KERNEL32!GetProcessHeap` at `0x180062e58`
- `KERNEL32!GetProcessHeap` at `0x180062e8d`
- `KERNEL32!GetProcessHeap` at `0x180062e58`
- `KERNEL32!GetProcessHeap` at `0x180062e8d`

## pseudocode

```c

```

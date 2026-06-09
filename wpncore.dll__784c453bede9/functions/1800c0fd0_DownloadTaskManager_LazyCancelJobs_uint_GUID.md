# DownloadTaskManager::LazyCancelJobs(uint,_GUID *)

- ea: `0x1800c0fd0`
- end: `0x1800c11ad`
- name: `?LazyCancelJobs@DownloadTaskManager@@UEAAJIPEAU_GUID@@@Z`
- size: `477`
- prototype: `__int64 __fastcall(DownloadTaskManager *__hidden this, unsigned int, struct _GUID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task`

## callees

- `0x180004e38`
- `0x1800a5748`
- `0x1800c059c`
- `0x1800c0fd0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1163`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c1163`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c107e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c107e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c10d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c111c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c10d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800c111c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c10e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c112a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c10e1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800c112a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800c110c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800c110c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c1143`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c1143`

## pseudocode

```c

```

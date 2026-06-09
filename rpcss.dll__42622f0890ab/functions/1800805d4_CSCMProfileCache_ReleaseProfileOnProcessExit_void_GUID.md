# CSCMProfileCache::ReleaseProfileOnProcessExit(void *,_GUID)

- ea: `0x1800805d4`
- end: `0x180080785`
- name: `?ReleaseProfileOnProcessExit@CSCMProfileCache@@QEAAJPEAXU_GUID@@@Z`
- size: `433`
- prototype: `int(CSCMProfileCache *__hidden this, void *, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800507c0`

## callees

- `0x180034540`
- `0x18007e3d4`
- `0x1800805d4`
- `0x1800b2bb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008070b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008070b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008075b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008075b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180080667`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180080667`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180080603`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180080603`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180080632`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008063b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180080632`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008063b`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800806fc`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x1800806fc`

## string_xrefs

- `0x1800806c4`: `CSCMProfileCache::ReleaseProfileOnProcessExit`
- `0x1800806cb`: `onecore\com\combase\rpcss\olescm\profiles.cxx`

## pseudocode

```c

```

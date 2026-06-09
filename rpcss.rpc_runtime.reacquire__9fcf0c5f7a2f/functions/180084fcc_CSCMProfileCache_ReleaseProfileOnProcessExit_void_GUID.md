# CSCMProfileCache::ReleaseProfileOnProcessExit(void *,_GUID)

- ea: `0x180084fcc`
- end: `0x1800851b1`
- name: `?ReleaseProfileOnProcessExit@CSCMProfileCache@@QEAAJPEAXU_GUID@@@Z`
- size: `485`
- prototype: `int(CSCMProfileCache *__hidden this, void *, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004c4b0`

## callees

- `0x180034260`
- `0x18008172c`
- `0x180084fcc`
- `0x1800b7e90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008512a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008512a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085180`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180085180`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180085071`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180085071`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180084ffb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180084ffb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180085030`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008503f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180085030`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008503f`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180085115`
- `api-ms-win-core-threadpool-private-l1-1-0!RegisterWaitForSingleObjectEx` at `0x180085115`

## string_xrefs

- `0x1800850e1`: `onecore\com\combase\rpcss\olescm\profiles.cxx`
- `0x1800850da`: `CSCMProfileCache::ReleaseProfileOnProcessExit`

## pseudocode

```c

```

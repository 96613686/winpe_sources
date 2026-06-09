# PfsIdleTaskMgrUnregisterInternal

- ea: `0x18006f950`
- end: `0x18006fa05`
- name: `PfsIdleTaskMgrUnregisterInternal`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180058d58`

## callees

- `0x180059264`
- `0x18006f950`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18006f963`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18006f963`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18006f9a1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18006f9a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f9aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f9b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f9aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f9b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f9ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f9ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f9ca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18006f9ef`

## pseudocode

```c

```

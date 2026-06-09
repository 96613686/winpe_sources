# DeletepJob(_WINLOGON_JOB * *,int)

- ea: `0x140035f30`
- end: `0x14003606b`
- name: `?DeletepJob@@YAXPEAPEAU_WINLOGON_JOB@@H@Z`
- size: `315`
- prototype: `void __fastcall(struct _WINLOGON_JOB **, int)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14003a054`
- `0x140042b78`
- `0x14005fbd0`
- `0x1400727a0`
- `0x140076178`
- `0x14007916c`
- `0x14007a1d0`

## callees

- `0x140035f30`
- `0x140036074`
- `0x14005fe8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140036052`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140036052`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140036044`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140036044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140035f83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140035f92`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140035f83`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140035f92`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x14003603b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x14003603b`
- `ntdll!RtlLeaveCriticalSection` at `0x14003601f`
- `ntdll!RtlLeaveCriticalSection` at `0x14003601f`
- `ntdll!RtlEnterCriticalSection` at `0x140035f4e`
- `ntdll!RtlEnterCriticalSection` at `0x140035f4e`
- `ntdll!RtlNtStatusToDosError` at `0x140035f56`
- `ntdll!RtlNtStatusToDosError` at `0x140036027`
- `ntdll!RtlNtStatusToDosError` at `0x140035f56`
- `ntdll!RtlNtStatusToDosError` at `0x140036027`

## pseudocode

```c

```

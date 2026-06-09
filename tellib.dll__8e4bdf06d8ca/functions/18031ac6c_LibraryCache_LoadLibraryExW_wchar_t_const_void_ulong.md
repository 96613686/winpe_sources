# LibraryCache::LoadLibraryExW(wchar_t const *,void *,ulong)

- ea: `0x18031ac6c`
- end: `0x18031adfc`
- name: `?LoadLibraryExW@LibraryCache@@QEAAPEAUHINSTANCE__@@PEB_WPEAXK@Z`
- size: `400`
- prototype: `HINSTANCE(LibraryCache *__hidden this, const wchar_t *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18031a604`

## callees

- `0x18012eac0`
- `0x18031ac6c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18031ad26`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18031ad26`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18031ad4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18031ade1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18031ad4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18031ade1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18031ac81`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18031ac81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18031acef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18031ad60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18031acef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18031ad60`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18031ad09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18031ad09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18031ad74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18031ad74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031ad3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18031ad3a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18031ad82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18031ad82`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18031acb8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18031acb8`

## pseudocode

```c

```

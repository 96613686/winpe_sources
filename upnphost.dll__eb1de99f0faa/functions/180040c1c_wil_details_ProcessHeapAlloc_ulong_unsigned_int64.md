# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180040c1c`
- end: `0x180040cb2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800373cc`
- `0x180040304`
- `0x180040428`
- `0x180042864`
- `0x180042ac8`

## callees

- `0x18003bc14`
- `0x180040c1c`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180040c65`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180040c65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040c30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180040c30`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180040c41`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180040c41`

## string_xrefs

- `0x180040c5e`: `ntdll.dll`

## pseudocode

```c

```

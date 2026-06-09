# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18008ce4c`
- end: `0x18008ceea`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18008cd8c`
- `0x1800a8bb0`
- `0x1800a8cdc`
- `0x1800a9a34`
- `0x1800a9c98`

## callees

- `0x18008ce4c`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18008ce95`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18008ce95`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008ceaa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008ceaa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ce60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18008ce60`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008ce71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18008ce71`

## string_xrefs

- `0x18008ce8e`: `ntdll.dll`

## pseudocode

```c

```

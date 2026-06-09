# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180036b40`
- end: `0x180036bd6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180024ba4`
- `0x180036244`
- `0x18003700c`
- `0x1800373a4`
- `0x180037c90`

## callees

- `0x180034dbc`
- `0x180036b40`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036b89`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180036b89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036b65`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036b65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036b54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036b54`

## string_xrefs

- `0x180036b82`: `ntdll.dll`

## pseudocode

```c

```

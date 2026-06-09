# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180038a34`
- end: `0x180038add`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180025f04`
- `0x1800380cc`
- `0x180038f4c`
- `0x180039300`
- `0x180039c2c`

## callees

- `0x180036b6c`
- `0x180038a34`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038a89`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180038a89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038a5f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038a5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038a48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038a48`

## string_xrefs

- `0x180038a82`: `ntdll.dll`

## pseudocode

```c

```

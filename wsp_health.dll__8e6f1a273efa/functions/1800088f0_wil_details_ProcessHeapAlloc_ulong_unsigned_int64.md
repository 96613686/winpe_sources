# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800088f0`
- end: `0x1800089a7`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800084cc`
- `0x1800085f4`
- `0x1800097e4`
- `0x180009c88`
- `0x18000aa18`

## callees

- `0x1800088f0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008945`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008945`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008960`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008960`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008904`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008904`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000891b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000891b`

## string_xrefs

- `0x18000893e`: `ntdll.dll`

## pseudocode

```c

```

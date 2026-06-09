# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008a00`
- end: `0x180008ab7`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800085dc`
- `0x180008704`
- `0x1800098f4`
- `0x180009d98`
- `0x18000ac58`

## callees

- `0x180008a00`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a55`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a55`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008a70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008a70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008a14`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008a2b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008a2b`

## string_xrefs

- `0x180008a4e`: `ntdll.dll`

## pseudocode

```c

```

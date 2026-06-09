# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18004aff4`
- end: `0x18004b095`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `161`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004ad08`
- `0x18004ae00`
- `0x18004af30`
- `0x180079f18`
- `0x180089750`
- `0x180089ca0`
- `0x180089ddc`
- `0x18008b114`

## callees

- `0x18004aff4`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004b05c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18004b05c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b071`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004b071`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b019`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004b019`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b008`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004b008`

## string_xrefs

- `0x18004b055`: `ntdll.dll`

## pseudocode

```c

```

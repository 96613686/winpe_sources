# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180021744`
- end: `0x1800217da`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180016ce8`
- `0x180021acc`
- `0x180021c44`
- `0x1800222dc`

## callees

- `0x18001ee2c`
- `0x180021744`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002178d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002178d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021769`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180021769`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021758`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021758`

## string_xrefs

- `0x180021786`: `ntdll.dll`

## pseudocode

```c

```

# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180034db0`
- end: `0x180034e46`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180023544`
- `0x180030cc0`
- `0x180030e6c`
- `0x18003a684`
- `0x18003a7c0`
- `0x18003f128`

## callees

- `0x180034db0`
- `0x180039168`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180034df9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180034df9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034dd5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034dd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034dc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034dc4`

## string_xrefs

- `0x180034df2`: `ntdll.dll`

## pseudocode

```c

```

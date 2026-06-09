# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180016e98`
- end: `0x180016f2e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180010740`
- `0x1800108a4`
- `0x1800170f4`
- `0x18001726c`
- `0x18001c8b0`

## callees

- `0x1800155a0`
- `0x180016e98`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016ee1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016ee1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016eac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016eac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016ebd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016ebd`

## string_xrefs

- `0x180016eda`: `ntdll.dll`

## pseudocode

```c

```

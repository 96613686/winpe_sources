# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18009a5d8`
- end: `0x18009a66e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180076b5c`
- `0x18009a128`
- `0x18009a24c`
- `0x18009cf64`
- `0x18009d1c8`

## callees

- `0x180097a30`
- `0x18009a5d8`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18009a621`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18009a621`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009a5fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009a5fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009a5ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18009a5ec`

## string_xrefs

- `0x18009a61a`: `ntdll.dll`

## pseudocode

```c

```

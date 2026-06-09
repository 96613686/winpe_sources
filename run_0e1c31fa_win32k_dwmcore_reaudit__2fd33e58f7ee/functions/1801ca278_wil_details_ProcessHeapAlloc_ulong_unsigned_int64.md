# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1801ca278`
- end: `0x1801ca316`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1801c9f70`
- `0x1801ca1d0`
- `0x18022b194`
- `0x18022b8cc`
- `0x18022ba44`

## callees

- `0x1801ca278`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801ca2c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801ca2c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801ca307`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801ca307`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ca28c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801ca28c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ca29d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801ca29d`

## string_xrefs

- `0x1801ca2ba`: `ntdll.dll`

## pseudocode

```c

```

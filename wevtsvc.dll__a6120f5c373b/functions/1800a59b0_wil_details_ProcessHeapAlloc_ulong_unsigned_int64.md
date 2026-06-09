# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800a59b0`
- end: `0x1800a5a4e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180083414`
- `0x1800a588c`
- `0x1800a6320`
- `0x1800a6498`
- `0x1800aa91c`

## callees

- `0x1800a59b0`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a59d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a59d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a59c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a59c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a5a0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a5a0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a59f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800a59f9`

## string_xrefs

- `0x1800a59f2`: `ntdll.dll`

## pseudocode

```c

```

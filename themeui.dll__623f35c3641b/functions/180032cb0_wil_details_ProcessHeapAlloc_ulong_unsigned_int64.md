# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180032cb0`
- end: `0x180032d4e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800133fc`
- `0x1800135dc`
- `0x1800137f8`
- `0x1800138d0`
- `0x180020bd4`
- `0x1800387c4`
- `0x1800388f4`
- `0x180039860`
- `0x180039cf0`

## callees

- `0x180032cb0`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180032cf9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180032cf9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032d0e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180032d0e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032cd5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180032cd5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032cc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180032cc4`

## string_xrefs

- `0x180032cf2`: `ntdll.dll`

## pseudocode

```c

```

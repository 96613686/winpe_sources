# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180031bd0`
- end: `0x180031c6e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `LPVOID __fastcall(DWORD dwFlags, SIZE_T dwBytes)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800273b0`
- `0x1800316f4`
- `0x180031818`
- `0x180032564`
- `0x1800327c8`

## callees

- `0x180031bd0`
- `0x1800bc010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180031c19`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180031c19`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031c2e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180031c2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031bf5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031bf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031be4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031be4`

## string_xrefs

- `0x180031c12`: `ntdll.dll`

## pseudocode

```c

```

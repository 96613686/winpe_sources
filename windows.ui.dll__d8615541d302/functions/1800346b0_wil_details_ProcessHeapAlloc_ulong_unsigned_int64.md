# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800346b0`
- end: `0x18003474e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180034608`
- `0x180044b34`
- `0x180058470`
- `0x180069978`
- `0x180069aa8`
- `0x18006bbd0`

## callees

- `0x1800346b0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003470e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003470e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800346f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800346f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800346c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800346c4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800346d5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800346d5`

## string_xrefs

- `0x1800346f2`: `ntdll.dll`

## pseudocode

```c

```

# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000cd28`
- end: `0x18000cdc6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000b210`
- `0x18000cc28`
- `0x18000e580`
- `0x180023310`
- `0x180052f48`
- `0x18006b560`
- `0x18006b8f8`

## callees

- `0x18000cd28`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cd86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cd86`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cd71`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cd71`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cd4d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000cd4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd3c`

## string_xrefs

- `0x18000cd6a`: `ntdll.dll`

## pseudocode

```c

```

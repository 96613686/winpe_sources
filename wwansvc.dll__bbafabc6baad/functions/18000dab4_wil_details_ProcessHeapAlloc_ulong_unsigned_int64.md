# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000dab4`
- end: `0x18000db52`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000d518`
- `0x18000d67c`
- `0x18000ea40`
- `0x18000eed0`
- `0x18001002c`

## callees

- `0x18000dab4`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000db12`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dafd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000dafd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dac8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dac8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dad9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000dad9`

## string_xrefs

- `0x18000daf6`: `ntdll.dll`

## pseudocode

```c

```

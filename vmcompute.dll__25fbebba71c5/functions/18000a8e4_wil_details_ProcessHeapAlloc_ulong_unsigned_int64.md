# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a8e4`
- end: `0x18000a99b`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000704c`
- `0x180007474`
- `0x1800097c8`
- `0x18000c8cc`
- `0x18000ea2c`

## callees

- `0x18000a8e4`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a939`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a939`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a954`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a954`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a90f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a90f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a8f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a8f8`

## string_xrefs

- `0x18000a932`: `ntdll.dll`

## pseudocode

```c

```

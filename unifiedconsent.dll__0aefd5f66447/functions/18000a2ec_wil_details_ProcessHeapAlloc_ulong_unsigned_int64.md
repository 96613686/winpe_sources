# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000a2ec`
- end: `0x18000a38a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800061b8`
- `0x180006588`
- `0x180008c10`
- `0x180009610`
- `0x18000c874`
- `0x18000e8d4`

## callees

- `0x18000a2ec`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a34a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a34a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a335`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a335`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a300`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a300`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a311`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a311`

## string_xrefs

- `0x18000a32e`: `ntdll.dll`

## pseudocode

```c

```

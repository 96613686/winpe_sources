# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14000b6bc`
- end: `0x14000b75a`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400091b8`
- `0x140009598`
- `0x14000a370`
- `0x14000a958`
- `0x14000cfe4`
- `0x14000eb90`

## callees

- `0x14000b6bc`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b705`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b705`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b71a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b71a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b6d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b6d0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000b6e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000b6e1`

## string_xrefs

- `0x14000b6fe`: `ntdll.dll`

## pseudocode

```c

```

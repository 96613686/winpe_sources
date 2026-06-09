# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003d9b8`
- end: `0x18003da56`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001d998`
- `0x18001dd6c`
- `0x18002d2c0`
- `0x1800314ac`
- `0x18004a3bc`
- `0x180057284`

## callees

- `0x18003d9b8`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003da16`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003da16`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003da01`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003da01`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d9dd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003d9dd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d9cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d9cc`

## string_xrefs

- `0x18003d9fa`: `ntdll.dll`

## pseudocode

```c

```

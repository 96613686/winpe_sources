# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180093800`
- end: `0x180093896`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800936a0`
- `0x1800938e4`
- `0x180093a5c`

## callees

- `0x180093068`
- `0x180093800`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180093814`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180093814`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180093825`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180093825`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180093849`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180093849`

## string_xrefs

- `0x180093842`: `ntdll.dll`

## pseudocode

```c

```

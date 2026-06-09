# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000c058`
- end: `0x18000c0ee`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000bdd4`
- `0x18000c480`
- `0x18000c818`
- `0x180026e4c`
- `0x18002ef9c`

## callees

- `0x180009c7c`
- `0x18000c058`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c0a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c0a1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c07d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000c07d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c06c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c06c`

## string_xrefs

- `0x18000c09a`: `ntdll.dll`

## pseudocode

```c

```

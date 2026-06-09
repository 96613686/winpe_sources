# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800435a0`
- end: `0x180043649`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18003985c`
- `0x180042bfc`
- `0x180042d20`
- `0x180045248`
- `0x1800454b8`

## callees

- `0x18003e278`
- `0x1800435a0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800435f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800435f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800435b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800435b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800435cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800435cb`

## string_xrefs

- `0x1800435ee`: `ntdll.dll`

## pseudocode

```c

```

# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x14004e5d0`
- end: `0x14004e687`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14004cbec`
- `0x140084724`
- `0x140123430`
- `0x140123568`
- `0x1401242a4`
- `0x140124750`

## callees

- `0x14004e5d0`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004e672`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004e672`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14004e625`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14004e625`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e5e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004e5e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14004e5fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14004e5fb`

## string_xrefs

- `0x14004e61e`: `ntdll.dll`

## pseudocode

```c

```

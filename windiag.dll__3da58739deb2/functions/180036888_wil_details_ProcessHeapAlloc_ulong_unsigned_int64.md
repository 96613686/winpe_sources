# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180036888`
- end: `0x180036926`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800345d8`
- `0x18003497c`
- `0x180035630`
- `0x180037f94`
- `0x18003983c`

## callees

- `0x180036888`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800368e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800368e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800368d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800368d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800368ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800368ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003689c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003689c`

## string_xrefs

- `0x1800368ca`: `ntdll.dll`

## pseudocode

```c

```

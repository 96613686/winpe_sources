# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180017888`
- end: `0x180017926`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800177d0`
- `0x180061588`
- `0x1800724d4`
- `0x180072604`
- `0x180073714`
- `0x180073850`

## callees

- `0x180017888`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800178e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800178e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800178d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800178d1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800178ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800178ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001789c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001789c`

## string_xrefs

- `0x1800178ca`: `ntdll.dll`

## pseudocode

```c

```

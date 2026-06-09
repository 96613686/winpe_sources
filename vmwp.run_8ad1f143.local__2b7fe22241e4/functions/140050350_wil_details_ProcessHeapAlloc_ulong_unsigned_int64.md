# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x140050350`
- end: `0x140050407`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14004dcac`
- `0x1400599f4`
- `0x140137350`
- `0x140137488`
- `0x1401381c4`
- `0x140138670`

## callees

- `0x140050350`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400503a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400503a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400503f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400503f2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14005037b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14005037b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140050364`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140050364`

## string_xrefs

- `0x14005039e`: `ntdll.dll`

## pseudocode

```c

```

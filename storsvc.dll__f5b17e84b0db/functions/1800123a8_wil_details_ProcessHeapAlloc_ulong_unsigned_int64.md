# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800123a8`
- end: `0x180012446`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800116bc`
- `0x1800120c0`
- `0x1800127e0`
- `0x180012b78`
- `0x180014d14`
- `0x180016a38`

## callees

- `0x1800123a8`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012406`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012406`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800123f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800123f1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800123cd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800123cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800123bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800123bc`

## string_xrefs

- `0x1800123ea`: `ntdll.dll`

## pseudocode

```c

```

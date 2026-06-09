# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18007d690`
- end: `0x18007d72e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007d8b0`
- `0x180081a2c`
- `0x180081b50`
- `0x180082ad4`
- `0x180082d38`

## callees

- `0x18007d690`
- `0x1800a2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d6ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d6ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007d6d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007d6d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007d6a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007d6a4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007d6b5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007d6b5`

## string_xrefs

- `0x18007d6d2`: `ntdll.dll`

## pseudocode

```c

```

# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180006828`
- end: `0x1800068c6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000504c`
- `0x180005cfc`
- `0x180006b68`
- `0x18001392c`
- `0x180019324`

## callees

- `0x180006828`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006871`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006871`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006886`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006886`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000683c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000683c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000684d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000684d`

## string_xrefs

- `0x18000686a`: `ntdll.dll`

## pseudocode

```c

```

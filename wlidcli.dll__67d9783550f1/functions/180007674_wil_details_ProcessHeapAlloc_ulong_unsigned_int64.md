# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007674`
- end: `0x180007712`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800063ec`
- `0x180007100`
- `0x180007264`
- `0x180008470`
- `0x1800088f4`
- `0x180009bcc`

## callees

- `0x180007674`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800076d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800076d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800076bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800076bd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007699`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007699`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007688`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007688`

## string_xrefs

- `0x1800076b6`: `ntdll.dll`

## pseudocode

```c

```

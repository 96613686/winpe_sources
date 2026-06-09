# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180018bf4`
- end: `0x180018c92`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002656c`
- `0x18003085c`
- `0x18003098c`
- `0x180031a10`
- `0x180031da8`

## callees

- `0x180018bf4`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018c52`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018c52`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018c3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180018c3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018c19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180018c19`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018c08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018c08`

## string_xrefs

- `0x180018c36`: `ntdll.dll`

## pseudocode

```c

```

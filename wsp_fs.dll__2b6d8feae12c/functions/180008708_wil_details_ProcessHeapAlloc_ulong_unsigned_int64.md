# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180008708`
- end: `0x1800087a6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800082fc`
- `0x180008424`
- `0x1800095b0`
- `0x180009a38`
- `0x18000a998`

## callees

- `0x180008708`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008751`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008751`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008766`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008766`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000871c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000871c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000872d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000872d`

## string_xrefs

- `0x18000874a`: `ntdll.dll`

## pseudocode

```c

```

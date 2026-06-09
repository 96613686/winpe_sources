# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800123e0`
- end: `0x18001247e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a744`
- `0x1800121dc`
- `0x180012e3c`
- `0x180012fb4`

## callees

- `0x1800123e0`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001243e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001243e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012429`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012429`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800123f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800123f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012405`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180012405`

## string_xrefs

- `0x180012422`: `ntdll.dll`

## pseudocode

```c

```

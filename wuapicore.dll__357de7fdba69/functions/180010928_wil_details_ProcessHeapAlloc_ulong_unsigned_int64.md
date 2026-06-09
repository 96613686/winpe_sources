# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180010928`
- end: `0x1800109c6`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800109cc`
- `0x18002f0dc`
- `0x18002f540`
- `0x180030274`

## callees

- `0x180010928`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010986`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010986`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010971`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010971`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001094d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001094d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001093c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001093c`

## string_xrefs

- `0x18001096a`: `ntdll.dll`

## pseudocode

```c

```

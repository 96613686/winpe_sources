# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180007b70`
- end: `0x180007c0e`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800092bc`
- `0x180009720`
- `0x18000a0cc`
- `0x18000acb8`
- `0x18000b5dc`

## callees

- `0x180007b70`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007bce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007bce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007bb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007bb9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007b95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180007b95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007b84`

## string_xrefs

- `0x180007bb2`: `ntdll.dll`

## pseudocode

```c

```

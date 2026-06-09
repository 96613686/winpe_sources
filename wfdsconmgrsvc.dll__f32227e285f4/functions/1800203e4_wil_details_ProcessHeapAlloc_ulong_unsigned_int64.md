# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800203e4`
- end: `0x180020482`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001fe88`
- `0x18001ffdc`
- `0x1800210d0`
- `0x180021554`
- `0x1800225b0`

## callees

- `0x1800203e4`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002042d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002042d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020442`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020442`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020409`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020409`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800203f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800203f8`

## string_xrefs

- `0x180020426`: `ntdll.dll`

## pseudocode

```c

```

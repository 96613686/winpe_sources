# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1800085e8`
- end: `0x180008686`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800081dc`
- `0x180008304`
- `0x180009490`
- `0x180009918`
- `0x18000a758`

## callees

- `0x1800085e8`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008631`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008631`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008646`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008646`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800085fc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000860d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000860d`

## string_xrefs

- `0x18000862a`: `ntdll.dll`

## pseudocode

```c

```

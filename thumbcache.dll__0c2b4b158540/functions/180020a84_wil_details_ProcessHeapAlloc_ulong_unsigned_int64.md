# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180020a84`
- end: `0x180020b22`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001eccc`
- `0x180020770`
- `0x1800208a0`
- `0x1800209d0`
- `0x1800260f8`
- `0x180026b0c`
- `0x180035020`
- `0x180035164`

## callees

- `0x180020a84`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020aa9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020aa9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020a98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020a98`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020acd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180020acd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020ae2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020ae2`

## string_xrefs

- `0x180020ac6`: `ntdll.dll`

## pseudocode

```c

```

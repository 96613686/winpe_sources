# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x1400302d0`
- end: `0x140030387`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140019108`
- `0x1400300bc`
- `0x1400305e8`
- `0x140030734`
- `0x140032b7c`

## callees

- `0x1400302d0`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140030325`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140030325`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140030340`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140030340`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400302e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400302e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400302fb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1400302fb`

## string_xrefs

- `0x14003031e`: `ntdll.dll`

## pseudocode

```c

```

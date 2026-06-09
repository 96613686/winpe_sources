# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18002d504`
- end: `0x18002d5bb`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `183`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800259f0`
- `0x180028d88`
- `0x18003edcc`
- `0x18005b66c`
- `0x18005be08`
- `0x18005bf54`
- `0x180068f70`

## callees

- `0x18002d504`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d574`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d574`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d559`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d559`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d518`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d518`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d52f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d52f`

## string_xrefs

- `0x18002d552`: `ntdll.dll`

## pseudocode

```c

```

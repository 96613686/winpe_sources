# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003813c`
- end: `0x1800381d5`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `153`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180037f64`
- `0x180038044`
- `0x180044adc`
- `0x180045734`
- `0x180051404`
- `0x18011f1b0`
- `0x1802798c4`

## callees

- `0x18003813c`
- `0x1802788e0`
- `0x1804a2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800381a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800381a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038150`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038150`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038161`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038161`

## string_xrefs

- `0x18003819d`: `ntdll.dll`

## pseudocode

```c

```

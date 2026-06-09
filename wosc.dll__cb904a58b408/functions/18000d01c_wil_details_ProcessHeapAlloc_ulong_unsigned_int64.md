# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000d01c`
- end: `0x18000d0b2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000beb8`
- `0x180011904`
- `0x18001c498`
- `0x18001ccc8`
- `0x18001ce2c`
- `0x18001e2f0`
- `0x18001e524`

## callees

- `0x18000760c`
- `0x18000d01c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d065`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d065`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d030`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d030`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d041`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000d041`

## string_xrefs

- `0x18000d05e`: `ntdll.dll`

## pseudocode

```c

```

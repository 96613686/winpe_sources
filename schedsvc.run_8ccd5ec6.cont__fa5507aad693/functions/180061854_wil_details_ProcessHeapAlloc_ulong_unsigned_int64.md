# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180061854`
- end: `0x1800618fd`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `169`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180058550`
- `0x1800586a8`
- `0x1800627c4`
- `0x180062ecc`
- `0x180064e98`

## callees

- `0x18005e538`
- `0x180061854`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800618a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800618a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061868`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180061868`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006187f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006187f`

## string_xrefs

- `0x1800618a2`: `ntdll.dll`

## pseudocode

```c

```

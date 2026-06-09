# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x180056034`
- end: `0x1800560d2`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18003a200`
- `0x180055f74`
- `0x180082800`
- `0x180083064`
- `0x180098b80`
- `0x180098f18`

## callees

- `0x180056034`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005607d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005607d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800560c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800560c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056048`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180056048`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056059`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180056059`

## string_xrefs

- `0x180056076`: `ntdll.dll`

## pseudocode

```c

```

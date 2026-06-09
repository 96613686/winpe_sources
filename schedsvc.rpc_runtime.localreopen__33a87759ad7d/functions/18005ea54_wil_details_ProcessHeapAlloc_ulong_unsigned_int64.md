# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18005ea54`
- end: `0x18005eaea`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `150`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180055be4`
- `0x180055d38`
- `0x18005f9a0`
- `0x180060074`
- `0x180061f14`

## callees

- `0x18005b914`
- `0x18005ea54`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005ea9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18005ea9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ea68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005ea68`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ea79`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ea79`

## string_xrefs

- `0x18005ea96`: `ntdll.dll`

## pseudocode

```c

```

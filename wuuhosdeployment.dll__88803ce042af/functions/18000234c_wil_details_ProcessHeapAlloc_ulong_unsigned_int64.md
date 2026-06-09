# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18000234c`
- end: `0x1800023ea`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `158`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003dc0`
- `0x180004220`
- `0x180004650`
- `0x180005b74`

## callees

- `0x18000234c`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800023aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800023aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002395`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180002395`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002371`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002371`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002360`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002360`

## string_xrefs

- `0x18000238e`: `ntdll.dll`

## pseudocode

```c

```

# wil::details::ProcessHeapAlloc(ulong,unsigned __int64)

- ea: `0x18003a24c`
- end: `0x18003a2ed`
- name: `?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z`
- size: `161`
- prototype: `void *__fastcall(DWORD dwFlags, SIZE_T dwBytes, unsigned __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180035300`
- `0x180036f44`
- `0x180039930`
- `0x180039c4c`
- `0x1800bd784`
- `0x1800bd8b4`

## callees

- `0x18003a24c`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a2c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a2c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003a2b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003a2b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a271`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003a271`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a260`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003a260`

## string_xrefs

- `0x18003a2ad`: `ntdll.dll`

## pseudocode

```c

```

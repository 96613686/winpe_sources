# wil::details_abi::heap_buffer::reserve(unsigned __int64)

- ea: `0x18006a540`
- end: `0x18006a69a`
- name: `?reserve@heap_buffer@details_abi@wil@@QEAA_N_K@Z`
- size: `346`
- prototype: `bool __fastcall(wil::details_abi::heap_buffer *__hidden this, unsigned __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180069230`
- `0x18006a3a4`
- `0x18006a480`
- `0x18006a4b0`

## callees

- `0x18006a540`
- `0x18006b490`
- `0x18006b5a8`
- `0x180129010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18006a629`
- `msvcrt!memcpy_s` at `0x18006a629`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006a5c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18006a5c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a5e7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a5e7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006a59e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006a59e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a587`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18006a587`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a56d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a56d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a657`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006a657`

## string_xrefs

- `0x18006a5c1`: `ntdll.dll`

## pseudocode

```c

```

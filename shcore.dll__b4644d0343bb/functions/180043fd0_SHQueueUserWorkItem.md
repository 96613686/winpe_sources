# SHQueueUserWorkItem

- ea: `0x180043fd0`
- end: `0x18004412a`
- name: `SHQueueUserWorkItem`
- size: `346`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpModuleName@<rcx>, int, LPCCH lpMultiByteStr, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180009260`
- `0x180043fd0`
- `0x180066910`
- `0x180066cfc`
- `0x180068d9c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004410e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004410e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180044059`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180044059`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800440f0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800440f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800440fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800440fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004411f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004411f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180044070`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180044070`

## pseudocode

```c

```

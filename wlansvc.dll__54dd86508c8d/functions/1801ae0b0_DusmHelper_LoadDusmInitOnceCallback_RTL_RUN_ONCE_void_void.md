# DusmHelper::LoadDusmInitOnceCallback(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x1801ae0b0`
- end: `0x1801ae1f0`
- name: `?LoadDusmInitOnceCallback@DusmHelper@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `320`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x1801ae0b0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801ae0d8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801ae0d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801ae136`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801ae19c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801ae136`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801ae19c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ae167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ae1d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ae167`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801ae1d9`

## string_xrefs

- `0x1801ae0cb`: `dusmapi.dll`

## pseudocode

```c

```

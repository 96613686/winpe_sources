# DoReboot(HWND__ *)

- ea: `0x1800bf760`
- end: `0x1800bf825`
- name: `?DoReboot@@YAJPEAUHWND__@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800be538`

## callees

- `0x1800bf760`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?IsMICLowProcess@@YAJPEAX@Z` at `0x1800bf776`
- `iertutil!__imp_?IsMICLowProcess@@YAJPEAX@Z` at `0x1800bf776`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bf81d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bf81d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bf7ea`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bf7ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf7a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf7f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf7a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf7f5`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800bf7d4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800bf7d4`
- `ext-ms-win-shell-shlwapi-l1-1-0!ShellMessageBoxA` at `0x1800bf79c`
- `ext-ms-win-shell-shlwapi-l1-1-0!ShellMessageBoxA` at `0x1800bf79c`

## string_xrefs

- `0x1800bf7cd`: `shell32.dll`

## pseudocode

```c

```

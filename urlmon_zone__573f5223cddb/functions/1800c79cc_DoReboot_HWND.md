# DoReboot(HWND__ *)

- ea: `0x1800c79cc`
- end: `0x1800c7abf`
- name: `?DoReboot@@YAJPEAUHWND__@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c673c`

## callees

- `0x1800c79cc`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?IsMICLowProcess@@YAJPEAX@Z` at `0x1800c79e2`
- `iertutil!__imp_?IsMICLowProcess@@YAJPEAX@Z` at `0x1800c79e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c7aae`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c7aae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c7a6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c7a6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7a80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7a1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7a80`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800c7a53`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x1800c7a53`
- `ext-ms-win-shell-shlwapi-l1-1-0!ShellMessageBoxA` at `0x1800c7a0e`
- `ext-ms-win-shell-shlwapi-l1-1-0!ShellMessageBoxA` at `0x1800c7a0e`

## string_xrefs

- `0x1800c7a4c`: `shell32.dll`

## pseudocode

```c

```

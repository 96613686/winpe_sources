# WDiagCheckProcessAccess(ulong)

- ea: `0x1801c8518`
- end: `0x1801c8753`
- name: `?WDiagCheckProcessAccess@@YAKK@Z`
- size: `571`
- prototype: `__int64 __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1801c9cd0`

## callees

- `0x180011530`
- `0x180029ed4`
- `0x180106340`
- `0x180107330`
- `0x18011a058`
- `0x1801c8518`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c85c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c862e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c85c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801c862e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801c8703`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801c8703`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801c85b5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801c85b5`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x1801c8684`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x1801c8684`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x1801c8624`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x1801c8624`

## pseudocode

```c

```

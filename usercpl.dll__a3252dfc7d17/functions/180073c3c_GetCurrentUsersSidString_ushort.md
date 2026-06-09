# GetCurrentUsersSidString(ushort * *)

- ea: `0x180073c3c`
- end: `0x180073ce4`
- name: `?GetCurrentUsersSidString@@YAJPEAPEAG@Z`
- size: `168`
- prototype: `__int64 __fastcall(LPWSTR *ppwsz)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180073cec`

## callees

- `0x18006e4f8`
- `0x180073c3c`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180073cb6`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180073cb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073c8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073cc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073ccc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073cc3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180073ccc`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180073c83`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180073c83`

## pseudocode

```c

```

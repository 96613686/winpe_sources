# BfspSetFileDirectorySecurityDescriptor

- ea: `0x180036ca8`
- end: `0x180036dce`
- name: `BfspSetFileDirectorySecurityDescriptor`
- size: `294`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180032518`
- `0x18003379c`

## callees

- `0x180031b50`
- `0x1800366b8`
- `0x180036adc`
- `0x180036ca8`
- `0x180036dd4`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180036d37`
- `msvcrt!swprintf_s` at `0x180036d37`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036ccb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036d89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036ccb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036d89`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036ce1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180036ce1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036d97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036d97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036db3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036da7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036da7`

## string_xrefs

- `0x180036d75`: `BfspSetSecurityDescriptor(%s) failed! Last Error = %#x`

## pseudocode

```c

```

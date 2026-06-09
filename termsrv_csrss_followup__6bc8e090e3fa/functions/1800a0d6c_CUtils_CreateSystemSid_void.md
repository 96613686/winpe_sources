# CUtils::CreateSystemSid(void * *)

- ea: `0x1800a0d6c`
- end: `0x1800a0db7`
- name: `?CreateSystemSid@CUtils@@SAJPEAPEAX@Z`
- size: `75`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1800a235c`

## callees

- `0x180030fac`
- `0x1800a0d6c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800a0d7b`
- `ntdll!RtlNtStatusToDosError` at `0x1800a0d7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0d89`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0d89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0d95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0d95`

## pseudocode

```c

```

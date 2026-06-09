# CUtils::CreateSystemSid(void * *)

- ea: `0x18000ec8c`
- end: `0x18000ecd7`
- name: `?CreateSystemSid@CUtils@@SAJPEAPEAX@Z`
- size: `75`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000eb30`

## callees

- `0x18000ec8c`
- `0x18000ece0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000eca3`
- `ntdll!RtlNtStatusToDosError` at `0x18000eca3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ecb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ecb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ecbd`

## pseudocode

```c

```

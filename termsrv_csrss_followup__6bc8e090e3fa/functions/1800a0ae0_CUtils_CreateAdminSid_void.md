# CUtils::CreateAdminSid(void * *)

- ea: `0x1800a0ae0`
- end: `0x1800a0b2b`
- name: `?CreateAdminSid@CUtils@@SAJPEAPEAX@Z`
- size: `75`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800a235c`
- `0x1800bf2e0`

## callees

- `0x1800310e0`
- `0x1800a0ae0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800a0aef`
- `ntdll!RtlNtStatusToDosError` at `0x1800a0aef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0afd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a0afd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0b09`

## pseudocode

```c

```

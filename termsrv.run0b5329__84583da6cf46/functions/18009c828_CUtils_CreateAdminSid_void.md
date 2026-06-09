# CUtils::CreateAdminSid(void * *)

- ea: `0x18009c828`
- end: `0x18009c860`
- name: `?CreateAdminSid@CUtils@@SAJPEAPEAX@Z`
- size: `56`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18009d4cc`
- `0x1800b8a00`

## callees

- `0x18002f534`
- `0x18009c828`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18009c837`
- `ntdll!RtlNtStatusToDosError` at `0x18009c837`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009c83f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009c83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c845`

## pseudocode

```c

```

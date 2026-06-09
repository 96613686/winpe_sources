# CUtils::CreateSystemSid(void * *)

- ea: `0x18000e9ec`
- end: `0x18000ea24`
- name: `?CreateSystemSid@CUtils@@SAJPEAPEAX@Z`
- size: `56`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18000e8b8`

## callees

- `0x18000e9ec`
- `0x18000ea2c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000ea02`
- `ntdll!RtlNtStatusToDosError` at `0x18000ea02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea10`

## pseudocode

```c

```

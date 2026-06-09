# CUtils::CreateSystemSid(void * *)

- ea: `0x18009ca6c`
- end: `0x18009caa4`
- name: `?CreateSystemSid@CUtils@@SAJPEAPEAX@Z`
- size: `56`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18009d4cc`

## callees

- `0x18002f404`
- `0x18009ca6c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18009ca7b`
- `ntdll!RtlNtStatusToDosError` at `0x18009ca7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009ca83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009ca83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ca89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ca89`

## pseudocode

```c

```

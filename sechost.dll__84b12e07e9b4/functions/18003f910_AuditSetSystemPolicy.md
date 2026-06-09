# AuditSetSystemPolicy

- ea: `0x18003f910`
- end: `0x18003f94c`
- name: `AuditSetSystemPolicy`
- size: `60`
- prototype: `BOOLEAN __stdcall(PCAUDIT_POLICY_INFORMATION pAuditPolicy, ULONG dwPolicyCount)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18003efb4`
- `0x18003f910`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003f925`
- `ntdll!RtlNtStatusToDosError` at `0x18003f925`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f93b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f93b`

## pseudocode

```c

```

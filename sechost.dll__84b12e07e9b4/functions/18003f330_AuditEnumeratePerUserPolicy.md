# AuditEnumeratePerUserPolicy

- ea: `0x18003f330`
- end: `0x18003f387`
- name: `AuditEnumeratePerUserPolicy`
- size: `87`
- prototype: `BOOLEAN __stdcall(PPOLICY_AUDIT_SID_ARRAY *ppAuditSidArray)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x18003f330`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003f360`
- `ntdll!RtlNtStatusToDosError` at `0x18003f360`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f376`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f376`
- `RPCRT4!NdrClientCall3` at `0x18003f353`
- `RPCRT4!NdrClientCall3` at `0x18003f353`

## pseudocode

```c

```

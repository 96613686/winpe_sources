# AuditQuerySecurity

- ea: `0x18003f660`
- end: `0x18003f6fa`
- name: `AuditQuerySecurity`
- size: `154`
- prototype: `BOOLEAN __stdcall(SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR *ppSecurityDescriptor)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18003f660`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003f6c9`
- `ntdll!RtlNtStatusToDosError` at `0x18003f6c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f6e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f6e3`
- `RPCRT4!NdrClientCall3` at `0x18003f6a7`
- `RPCRT4!NdrClientCall3` at `0x18003f6a7`

## pseudocode

```c

```

# AuditSetSecurity

- ea: `0x18003f800`
- end: `0x18003f8fe`
- name: `AuditSetSecurity`
- size: `254`
- prototype: `BOOLEAN __stdcall(SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18003f800`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003f876`
- `ntdll!RtlNtStatusToDosError` at `0x18003f8bd`
- `ntdll!RtlNtStatusToDosError` at `0x18003f876`
- `ntdll!RtlNtStatusToDosError` at `0x18003f8bd`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18003f828`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18003f86a`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18003f828`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18003f86a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f8e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f8e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f848`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f848`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f8db`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f8db`
- `RPCRT4!NdrClientCall3` at `0x18003f8b0`
- `RPCRT4!NdrClientCall3` at `0x18003f8b0`

## pseudocode

```c

```

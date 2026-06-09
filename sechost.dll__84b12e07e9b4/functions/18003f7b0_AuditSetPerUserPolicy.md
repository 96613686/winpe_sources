# AuditSetPerUserPolicy

- ea: `0x18003f7b0`
- end: `0x18003f7f9`
- name: `AuditSetPerUserPolicy`
- size: `73`
- prototype: `BOOLEAN __stdcall(const PSID pSid, PCAUDIT_POLICY_INFORMATION pAuditPolicy, ULONG dwPolicyCount)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x18003efb4`
- `0x18003f7b0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003f7da`
- `ntdll!RtlNtStatusToDosError` at `0x18003f7da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f7be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f7be`

## pseudocode

```c

```

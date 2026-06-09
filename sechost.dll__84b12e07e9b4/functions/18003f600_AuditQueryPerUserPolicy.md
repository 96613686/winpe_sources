# AuditQueryPerUserPolicy

- ea: `0x18003f600`
- end: `0x18003f65a`
- name: `AuditQueryPerUserPolicy`
- size: `90`
- prototype: `BOOLEAN __stdcall(const PSID pSid, const GUID *pSubCategoryGuids, ULONG dwPolicyCount, PAUDIT_POLICY_INFORMATION *ppAuditPolicy)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x18003ef60`
- `0x18003f600`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003f62c`
- `ntdll!RtlNtStatusToDosError` at `0x18003f62c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f64d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f64d`

## pseudocode

```c

```

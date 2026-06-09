# AuditComputeEffectivePolicyBySid

- ea: `0x18003f0a0`
- end: `0x18003f211`
- name: `AuditComputeEffectivePolicyBySid`
- size: `369`
- prototype: `BOOLEAN __stdcall(const PSID pSid, const GUID *pSubCategoryGuids, ULONG dwPolicyCount, PAUDIT_POLICY_INFORMATION *ppAuditPolicy)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18003ef60`
- `0x18003f0a0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003f0fe`
- `ntdll!RtlNtStatusToDosError` at `0x18003f1a8`
- `ntdll!RtlNtStatusToDosError` at `0x18003f0fe`
- `ntdll!RtlNtStatusToDosError` at `0x18003f1a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f1f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f1f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f18e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f1cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f1df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f18e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f1cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f1df`

## pseudocode

```c

```

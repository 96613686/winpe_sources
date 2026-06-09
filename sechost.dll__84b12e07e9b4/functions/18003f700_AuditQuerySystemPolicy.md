# AuditQuerySystemPolicy

- ea: `0x18003f700`
- end: `0x18003f753`
- name: `AuditQuerySystemPolicy`
- size: `83`
- prototype: `BOOLEAN __stdcall(const GUID *pSubCategoryGuids, ULONG dwPolicyCount, PAUDIT_POLICY_INFORMATION *ppAuditPolicy)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18003ef60`
- `0x18003f700`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18003f734`
- `ntdll!RtlNtStatusToDosError` at `0x18003f734`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f70d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f70d`

## pseudocode

```c

```

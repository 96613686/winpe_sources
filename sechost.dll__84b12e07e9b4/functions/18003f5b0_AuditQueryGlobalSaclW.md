# AuditQueryGlobalSaclW

- ea: `0x18003f5b0`
- end: `0x18003f5fa`
- name: `AuditQueryGlobalSaclW`
- size: `74`
- prototype: `BOOLEAN __stdcall(PCWSTR ObjectTypeName, PACL *Acl)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18003f5b0`
- `0x18003f954`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18003f5dd`
- `ntdll!RtlInitUnicodeString` at `0x18003f5dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f5cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f5cd`

## pseudocode

```c

```

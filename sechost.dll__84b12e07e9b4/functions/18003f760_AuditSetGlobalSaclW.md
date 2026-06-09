# AuditSetGlobalSaclW

- ea: `0x18003f760`
- end: `0x18003f7aa`
- name: `AuditSetGlobalSaclW`
- size: `74`
- prototype: `BOOLEAN __stdcall(PCWSTR ObjectTypeName, PACL Acl)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18003f760`
- `0x18003fa28`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18003f78d`
- `ntdll!RtlInitUnicodeString` at `0x18003f78d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f77d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f77d`

## pseudocode

```c

```

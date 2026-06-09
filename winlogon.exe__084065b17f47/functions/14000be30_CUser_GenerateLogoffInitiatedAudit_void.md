# CUser::GenerateLogoffInitiatedAudit(void)

- ea: `0x14000be30`
- end: `0x14000c014`
- name: `?GenerateLogoffInitiatedAudit@CUser@@QEAAKXZ`
- size: `484`
- prototype: `unsigned int __fastcall(CUser *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140052c20`

## callees

- `0x14000be30`
- `0x14000d4e0`
- `0x140053720`
- `0x1400544e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009d13f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c002`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14009d13f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000bffa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14009d16f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000bffa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14009d16f`
- `AUTHZ!AuthziInitializeAuditParams` at `0x14000bf31`
- `AUTHZ!AuthziInitializeAuditParams` at `0x14000bf31`
- `AUTHZ!AuthziFreeAuditEventType` at `0x14000bfcb`
- `AUTHZ!AuthziFreeAuditEventType` at `0x14009d15f`
- `AUTHZ!AuthziFreeAuditEventType` at `0x14000bfcb`
- `AUTHZ!AuthziFreeAuditEventType` at `0x14009d15f`
- `AUTHZ!AuthziInitializeAuditEvent` at `0x14000bf91`
- `AUTHZ!AuthziInitializeAuditEvent` at `0x14000bf91`
- `AUTHZ!AuthziInitializeAuditEventType` at `0x14000bede`
- `AUTHZ!AuthziInitializeAuditEventType` at `0x14000bede`
- `AUTHZ!AuthzFreeAuditEvent` at `0x14000c00c`
- `AUTHZ!AuthzFreeAuditEvent` at `0x14009d14f`
- `AUTHZ!AuthzFreeAuditEvent` at `0x14000c00c`
- `AUTHZ!AuthzFreeAuditEvent` at `0x14009d14f`
- `AUTHZ!AuthziLogAuditEvent` at `0x14000bfa9`
- `AUTHZ!AuthziLogAuditEvent` at `0x14000bfa9`

## string_xrefs

- `0x14000bf1a`: `Security`

## pseudocode

```c

```

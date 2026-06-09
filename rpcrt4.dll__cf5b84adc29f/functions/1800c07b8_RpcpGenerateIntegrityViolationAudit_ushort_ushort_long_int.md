# RpcpGenerateIntegrityViolationAudit(ushort *,ushort *,long,int)

- ea: `0x1800c07b8`
- end: `0x1800c0981`
- name: `?RpcpGenerateIntegrityViolationAudit@@YAXPEAG0JH@Z`
- size: `457`
- prototype: `void(unsigned __int16 *, unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180095234`

## callees

- `0x1800c0220`
- `0x1800c03b0`
- `0x1800c07b8`
- `0x1800ceca9`
- `0x1800ceda0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c0951`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c0951`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEventType` at `0x1800c084f`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEventType` at `0x1800c084f`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditParams` at `0x1800c08a2`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditParams` at `0x1800c08a2`
- `ext-ms-win-authz-context-l1-1-0!AuthziLogAuditEvent` at `0x1800c090f`
- `ext-ms-win-authz-context-l1-1-0!AuthziLogAuditEvent` at `0x1800c090f`
- `ext-ms-win-authz-context-l1-1-0!AuthzFreeAuditEvent` at `0x1800c0925`
- `ext-ms-win-authz-context-l1-1-0!AuthzFreeAuditEvent` at `0x1800c0925`
- `ext-ms-win-authz-context-l1-1-0!AuthziFreeAuditEventType` at `0x1800c093b`
- `ext-ms-win-authz-context-l1-1-0!AuthziFreeAuditEventType` at `0x1800c093b`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEvent` at `0x1800c08f5`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEvent` at `0x1800c08f5`

## string_xrefs

- `0x1800c0870`: `Security`

## pseudocode

```c

```

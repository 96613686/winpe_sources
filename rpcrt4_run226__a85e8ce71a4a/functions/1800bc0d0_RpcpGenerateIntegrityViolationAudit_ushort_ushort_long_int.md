# RpcpGenerateIntegrityViolationAudit(ushort *,ushort *,long,int)

- ea: `0x1800bc0d0`
- end: `0x1800bc26e`
- name: `?RpcpGenerateIntegrityViolationAudit@@YAXPEAG0JH@Z`
- size: `414`
- prototype: `void(unsigned __int16 *, unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800908bc`

## callees

- `0x1800bbbdc`
- `0x1800bbd38`
- `0x1800bc0d0`
- `0x1800ca049`
- `0x1800ca140`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc245`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bc245`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEventType` at `0x1800bc167`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEventType` at `0x1800bc167`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditParams` at `0x1800bc1b4`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditParams` at `0x1800bc1b4`
- `ext-ms-win-authz-context-l1-1-0!AuthziLogAuditEvent` at `0x1800bc215`
- `ext-ms-win-authz-context-l1-1-0!AuthziLogAuditEvent` at `0x1800bc215`
- `ext-ms-win-authz-context-l1-1-0!AuthzFreeAuditEvent` at `0x1800bc225`
- `ext-ms-win-authz-context-l1-1-0!AuthzFreeAuditEvent` at `0x1800bc225`
- `ext-ms-win-authz-context-l1-1-0!AuthziFreeAuditEventType` at `0x1800bc235`
- `ext-ms-win-authz-context-l1-1-0!AuthziFreeAuditEventType` at `0x1800bc235`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEvent` at `0x1800bc201`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEvent` at `0x1800bc201`

## string_xrefs

- `0x1800bc182`: `Security`

## pseudocode

```c

```

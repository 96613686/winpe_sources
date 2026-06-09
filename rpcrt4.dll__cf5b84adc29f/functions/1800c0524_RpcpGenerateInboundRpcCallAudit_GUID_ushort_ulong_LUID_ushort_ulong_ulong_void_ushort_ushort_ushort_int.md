# RpcpGenerateInboundRpcCallAudit(_GUID *,ushort *,ulong,_LUID *,ushort *,ulong,ulong,void *,ushort,ushort *,ushort *,int)

- ea: `0x1800c0524`
- end: `0x1800c07b2`
- name: `?RpcpGenerateInboundRpcCallAudit@@YAXPEAU_GUID@@PEAGKPEAU_LUID@@1KKPEAXG11H@Z`
- size: `654`
- prototype: `void __fastcall(struct _GUID *, unsigned __int16 *, unsigned int, struct _LUID *, unsigned __int16 *, unsigned int, unsigned int, void *, unsigned __int16, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b2f34`

## callees

- `0x1800c0220`
- `0x1800c03b0`
- `0x1800c0524`
- `0x1800ceca9`
- `0x1800ceda0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c077a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c077a`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEventType` at `0x1800c05da`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEventType` at `0x1800c05da`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditParams` at `0x1800c06d1`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditParams` at `0x1800c06d1`
- `ext-ms-win-authz-context-l1-1-0!AuthziLogAuditEvent` at `0x1800c073b`
- `ext-ms-win-authz-context-l1-1-0!AuthziLogAuditEvent` at `0x1800c073b`
- `ext-ms-win-authz-context-l1-1-0!AuthzFreeAuditEvent` at `0x1800c0750`
- `ext-ms-win-authz-context-l1-1-0!AuthzFreeAuditEvent` at `0x1800c0750`
- `ext-ms-win-authz-context-l1-1-0!AuthziFreeAuditEventType` at `0x1800c0765`
- `ext-ms-win-authz-context-l1-1-0!AuthziFreeAuditEventType` at `0x1800c0765`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEvent` at `0x1800c0722`
- `ext-ms-win-authz-context-l1-1-0!AuthziInitializeAuditEvent` at `0x1800c0722`

## string_xrefs

- `0x1800c05fd`: `Security`

## pseudocode

```c

```

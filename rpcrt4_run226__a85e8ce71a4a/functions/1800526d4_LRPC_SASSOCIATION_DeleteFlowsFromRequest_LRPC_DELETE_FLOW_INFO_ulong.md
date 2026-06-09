# LRPC_SASSOCIATION::DeleteFlowsFromRequest(_LRPC_DELETE_FLOW_INFO *,ulong)

- ea: `0x1800526d4`
- end: `0x1800527e1`
- name: `?DeleteFlowsFromRequest@LRPC_SASSOCIATION@@QEAAXPEAU_LRPC_DELETE_FLOW_INFO@@K@Z`
- size: `269`
- prototype: `void __fastcall(LRPC_SASSOCIATION *this, struct _LRPC_DELETE_FLOW_INFO *, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180054300`

## callees

- `0x18004cc58`
- `0x180050ce4`
- `0x1800526d4`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180052761`
- `ntdll!RtlLeaveCriticalSection` at `0x180052761`
- `ntdll!RtlEnterCriticalSection` at `0x180052726`
- `ntdll!RtlEnterCriticalSection` at `0x180052726`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180052791`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180052791`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180052772`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180052772`

## pseudocode

```c

```

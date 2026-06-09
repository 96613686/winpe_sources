# LRPC_SASSOCIATION::DeleteFlowsFromRequest(_LRPC_DELETE_FLOW_INFO *,ulong)

- ea: `0x18000d520`
- end: `0x18000d646`
- name: `?DeleteFlowsFromRequest@LRPC_SASSOCIATION@@QEAAXPEAU_LRPC_DELETE_FLOW_INFO@@K@Z`
- size: `294`
- prototype: `void __fastcall(LRPC_SASSOCIATION *this, struct _LRPC_DELETE_FLOW_INFO *, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18009f130`

## callees

- `0x18000d520`
- `0x18000e524`
- `0x18001664c`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18000d5b3`
- `ntdll!RtlLeaveCriticalSection` at `0x18000d5b3`
- `ntdll!RtlEnterCriticalSection` at `0x18000d572`
- `ntdll!RtlEnterCriticalSection` at `0x18000d572`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d5ef`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000d5ef`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d5ca`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000d5ca`

## pseudocode

```c

```

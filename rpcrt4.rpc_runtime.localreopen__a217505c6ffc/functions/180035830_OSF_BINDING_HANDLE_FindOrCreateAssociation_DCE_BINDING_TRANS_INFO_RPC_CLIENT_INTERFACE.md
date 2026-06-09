# OSF_BINDING_HANDLE::FindOrCreateAssociation(DCE_BINDING *,TRANS_INFO *,_RPC_CLIENT_INTERFACE *)

- ea: `0x180035830`
- end: `0x180035b35`
- name: `?FindOrCreateAssociation@OSF_BINDING_HANDLE@@QEAAPEAVOSF_CASSOCIATION@@PEAVDCE_BINDING@@PEAVTRANS_INFO@@PEAU_RPC_CLIENT_INTERFACE@@@Z`
- size: `773`
- prototype: `struct OSF_CASSOCIATION *(OSF_BINDING_HANDLE *__hidden this, struct DCE_BINDING *, struct TRANS_INFO *, struct _RPC_CLIENT_INTERFACE *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1800af198`
- `0x1800afaf8`

## callees

- `0x180007fec`
- `0x18000fd70`
- `0x180023020`
- `0x1800250a8`
- `0x180035830`
- `0x180035b3c`
- `0x180035d54`
- `0x180035dd4`
- `0x180035ff4`
- `0x1800a79b0`
- `0x1800ba980`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800359a9`
- `ntdll!RtlLeaveCriticalSection` at `0x180035a0d`
- `ntdll!RtlLeaveCriticalSection` at `0x180035ad1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800359a9`
- `ntdll!RtlLeaveCriticalSection` at `0x180035a0d`
- `ntdll!RtlLeaveCriticalSection` at `0x180035ad1`
- `ntdll!RtlEnterCriticalSection` at `0x180035879`
- `ntdll!RtlEnterCriticalSection` at `0x180035879`

## pseudocode

```c

```

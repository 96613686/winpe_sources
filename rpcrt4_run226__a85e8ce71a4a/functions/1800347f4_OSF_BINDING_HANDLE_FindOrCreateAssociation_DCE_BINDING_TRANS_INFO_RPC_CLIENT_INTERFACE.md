# OSF_BINDING_HANDLE::FindOrCreateAssociation(DCE_BINDING *,TRANS_INFO *,_RPC_CLIENT_INTERFACE *)

- ea: `0x1800347f4`
- end: `0x180034ae0`
- name: `?FindOrCreateAssociation@OSF_BINDING_HANDLE@@QEAAPEAVOSF_CASSOCIATION@@PEAVDCE_BINDING@@PEAVTRANS_INFO@@PEAU_RPC_CLIENT_INTERFACE@@@Z`
- size: `748`
- prototype: `struct OSF_CASSOCIATION *(OSF_BINDING_HANDLE *__hidden this, struct DCE_BINDING *, struct TRANS_INFO *, struct _RPC_CLIENT_INTERFACE *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1800ab758`
- `0x1800ac06c`

## callees

- `0x180021e70`
- `0x18002419c`
- `0x1800347f4`
- `0x180034ae8`
- `0x180034ce8`
- `0x180034d60`
- `0x180034f5c`
- `0x18004f480`
- `0x180067c7c`
- `0x1800a4290`
- `0x1800b67ec`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180034967`
- `ntdll!RtlLeaveCriticalSection` at `0x1800349c4`
- `ntdll!RtlLeaveCriticalSection` at `0x180034a82`
- `ntdll!RtlLeaveCriticalSection` at `0x180034967`
- `ntdll!RtlLeaveCriticalSection` at `0x1800349c4`
- `ntdll!RtlLeaveCriticalSection` at `0x180034a82`
- `ntdll!RtlEnterCriticalSection` at `0x18003483d`
- `ntdll!RtlEnterCriticalSection` at `0x18003483d`

## pseudocode

```c

```

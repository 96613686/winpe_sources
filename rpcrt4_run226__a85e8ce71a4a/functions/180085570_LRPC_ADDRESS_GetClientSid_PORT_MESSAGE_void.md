# LRPC_ADDRESS::GetClientSid(_PORT_MESSAGE *,void * *)

- ea: `0x180085570`
- end: `0x18008574e`
- name: `?GetClientSid@LRPC_ADDRESS@@QEAAJPEAU_PORT_MESSAGE@@PEAPEAX@Z`
- size: `478`
- prototype: `__int64 __fastcall(LRPC_ADDRESS *__hidden this, struct _PORT_MESSAGE *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180085440`

## callees

- `0x180021ce0`
- `0x180021e70`
- `0x180022870`
- `0x1800274e0`
- `0x1800283bc`
- `0x180085570`

## import_xrefs

- `ntdll!NtAlpcQueryInformationMessage` at `0x1800855cc`
- `ntdll!NtAlpcQueryInformationMessage` at `0x1800856d6`
- `ntdll!NtAlpcQueryInformationMessage` at `0x1800855cc`
- `ntdll!NtAlpcQueryInformationMessage` at `0x1800856d6`

## pseudocode

```c

```

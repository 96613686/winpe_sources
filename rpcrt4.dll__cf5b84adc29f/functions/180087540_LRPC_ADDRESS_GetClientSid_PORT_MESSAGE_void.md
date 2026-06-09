# LRPC_ADDRESS::GetClientSid(_PORT_MESSAGE *,void * *)

- ea: `0x180087540`
- end: `0x18008772b`
- name: `?GetClientSid@LRPC_ADDRESS@@QEAAJPEAU_PORT_MESSAGE@@PEAPEAX@Z`
- size: `491`
- prototype: `__int64 __fastcall(LRPC_ADDRESS *__hidden this, struct _PORT_MESSAGE *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180087400`

## callees

- `0x180022e80`
- `0x180023020`
- `0x180023a40`
- `0x180028670`
- `0x1800295d8`
- `0x180087540`

## import_xrefs

- `ntdll!NtAlpcQueryInformationMessage` at `0x18008759c`
- `ntdll!NtAlpcQueryInformationMessage` at `0x1800876ad`
- `ntdll!NtAlpcQueryInformationMessage` at `0x18008759c`
- `ntdll!NtAlpcQueryInformationMessage` at `0x1800876ad`

## pseudocode

```c

```

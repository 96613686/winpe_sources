# WlSecureDesktoprSimulateSAS

- ea: `0x140094e90`
- end: `0x140094f60`
- name: `WlSecureDesktoprSimulateSAS`
- size: `208`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x140094894`
- `0x140094e90`
- `0x14009b5c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x140094ede`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x140094ede`
- `RPCRT4!RpcRevertToSelf` at `0x140094f1c`
- `RPCRT4!RpcRevertToSelf` at `0x140094f24`
- `RPCRT4!RpcRevertToSelf` at `0x140094f1c`
- `RPCRT4!RpcRevertToSelf` at `0x140094f24`
- `RPCRT4!RpcImpersonateClient` at `0x140094ef6`
- `RPCRT4!RpcImpersonateClient` at `0x140094ef6`
- `ntdll!RtlNtStatusToDosError` at `0x140094f14`
- `ntdll!RtlNtStatusToDosError` at `0x140094f50`
- `ntdll!RtlNtStatusToDosError` at `0x140094f14`
- `ntdll!RtlNtStatusToDosError` at `0x140094f50`

## pseudocode

```c

```

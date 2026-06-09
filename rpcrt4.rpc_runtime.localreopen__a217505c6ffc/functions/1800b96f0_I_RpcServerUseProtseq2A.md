# I_RpcServerUseProtseq2A

- ea: `0x1800b96f0`
- end: `0x1800b989f`
- name: `I_RpcServerUseProtseq2A`
- size: `431`
- prototype: `RPC_STATUS __stdcall(RPC_CSTR NetworkAddress, RPC_CSTR Protseq, unsigned int MaxCalls, void *SecurityDescriptor, void *Policy)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b9fa0`
- `0x1800ba030`

## callees

- `0x18000cb1c`
- `0x1800258b4`
- `0x18006d460`
- `0x18008f200`
- `0x180098ba0`
- `0x18009b5cc`
- `0x1800aa300`
- `0x1800b96f0`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `KERNELBASE!lstrlenA` at `0x1800b9754`
- `KERNELBASE!lstrlenA` at `0x1800b9754`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800b9824`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800b9824`

## pseudocode

```c

```

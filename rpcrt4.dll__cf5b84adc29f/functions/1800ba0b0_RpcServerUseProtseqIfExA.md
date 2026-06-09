# RpcServerUseProtseqIfExA

- ea: `0x1800ba0b0`
- end: `0x1800ba22a`
- name: `RpcServerUseProtseqIfExA`
- size: `378`
- prototype: `RPC_STATUS __stdcall(RPC_CSTR Protseq, unsigned int MaxCalls, RPC_IF_HANDLE IfSpec, void *SecurityDescriptor, PRPC_POLICY Policy)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ba060`

## callees

- `0x1800258b4`
- `0x18006d460`
- `0x18009b5cc`
- `0x1800aa300`
- `0x1800ad900`
- `0x1800ba0b0`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `KERNELBASE!lstrlenA` at `0x1800ba103`
- `KERNELBASE!lstrlenA` at `0x1800ba103`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800ba1d6`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800ba1d6`

## pseudocode

```c

```

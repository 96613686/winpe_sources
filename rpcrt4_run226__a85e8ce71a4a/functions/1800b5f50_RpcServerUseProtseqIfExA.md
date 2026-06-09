# RpcServerUseProtseqIfExA

- ea: `0x1800b5f50`
- end: `0x1800b60bd`
- name: `RpcServerUseProtseqIfExA`
- size: `365`
- prototype: `RPC_STATUS __stdcall(RPC_CSTR Protseq, unsigned int MaxCalls, RPC_IF_HANDLE IfSpec, void *SecurityDescriptor, PRPC_POLICY Policy)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b5f00`

## callees

- `0x18002499c`
- `0x18005ceb0`
- `0x180097c3c`
- `0x1800a6a40`
- `0x1800a9f90`
- `0x1800b5f50`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `KERNELBASE!lstrlenA` at `0x1800b5fa3`
- `KERNELBASE!lstrlenA` at `0x1800b5fa3`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800b6070`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800b6070`

## pseudocode

```c

```

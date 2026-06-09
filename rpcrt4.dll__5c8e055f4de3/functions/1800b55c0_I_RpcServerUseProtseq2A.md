# I_RpcServerUseProtseq2A

- ea: `0x1800b55c0`
- end: `0x1800b5762`
- name: `I_RpcServerUseProtseq2A`
- size: `418`
- prototype: `RPC_STATUS __stdcall(RPC_CSTR NetworkAddress, RPC_CSTR Protseq, unsigned int MaxCalls, void *SecurityDescriptor, void *Policy)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b5e40`
- `0x1800b5ed0`

## callees

- `0x18002499c`
- `0x18005ceb0`
- `0x18006e120`
- `0x180093ef4`
- `0x180095650`
- `0x180097c3c`
- `0x1800a6a40`
- `0x1800b55c0`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `KERNELBASE!lstrlenA` at `0x1800b5624`
- `KERNELBASE!lstrlenA` at `0x1800b5624`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800b56ee`
- `ntdll!RtlMultiByteToUnicodeN` at `0x1800b56ee`

## pseudocode

```c

```

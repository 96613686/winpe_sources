# RpcServerUseAllProtseqsEx

- ea: `0x1800ad640`
- end: `0x1800ad7dc`
- name: `RpcServerUseAllProtseqsEx`
- size: `412`
- prototype: `RPC_STATUS __stdcall(unsigned int MaxCalls, void *SecurityDescriptor, PRPC_POLICY Policy)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ad610`

## callees

- `0x18001e690`
- `0x18001e7d0`
- `0x1800258b4`
- `0x18008f718`
- `0x180098ebc`
- `0x180098fd0`
- `0x1800ad640`

## import_xrefs

- `ntdll!_wcsnicmp` at `0x1800ad6f2`
- `ntdll!_wcsnicmp` at `0x1800ad718`
- `ntdll!_wcsnicmp` at `0x1800ad6f2`
- `ntdll!_wcsnicmp` at `0x1800ad718`

## pseudocode

```c

```

# RpcServerUseProtseqIfExW

- ea: `0x1800ad900`
- end: `0x1800ada1c`
- name: `RpcServerUseProtseqIfExW`
- size: `284`
- prototype: `RPC_STATUS __stdcall(RPC_WSTR Protseq, unsigned int MaxCalls, RPC_IF_HANDLE IfSpec, void *SecurityDescriptor, PRPC_POLICY Policy)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ada30`
- `0x1800ba0b0`

## callees

- `0x1800258b4`
- `0x18008ece0`
- `0x1800a7ed8`
- `0x1800ad900`

## import_xrefs

- `ntdll!_wcsnicmp` at `0x1800ad9a2`
- `ntdll!_wcsnicmp` at `0x1800ad9a2`
- `ntdll!RtlFreeUnicodeString` at `0x1800ad9b7`
- `ntdll!RtlFreeUnicodeString` at `0x1800ad9ec`
- `ntdll!RtlFreeUnicodeString` at `0x1800ad9b7`
- `ntdll!RtlFreeUnicodeString` at `0x1800ad9ec`

## pseudocode

```c

```

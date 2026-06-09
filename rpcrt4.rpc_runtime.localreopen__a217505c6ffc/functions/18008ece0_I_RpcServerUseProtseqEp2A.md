# I_RpcServerUseProtseqEp2A

- ea: `0x18008ece0`
- end: `0x18008ef56`
- name: `I_RpcServerUseProtseqEp2A`
- size: `630`
- prototype: `RPC_STATUS __stdcall(RPC_CSTR NetworkAddress, RPC_CSTR Protseq, unsigned int MaxCalls, RPC_CSTR Endpoint, void *SecurityDescriptor, void *Policy)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008ec80`
- `0x1800ad840`
- `0x1800ad900`
- `0x1800ba000`

## callees

- `0x18000cb1c`
- `0x1800258b4`
- `0x18006d460`
- `0x18008ece0`
- `0x18008f670`
- `0x180098ba0`
- `0x18009b5cc`
- `0x1800aa300`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `KERNELBASE!lstrlenA` at `0x18008ed7f`
- `KERNELBASE!lstrlenA` at `0x18008ed7f`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18008ee4f`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18008ee4f`
- `ntdll!RtlFreeUnicodeString` at `0x18008ed53`
- `ntdll!RtlFreeUnicodeString` at `0x18008ed69`
- `ntdll!RtlFreeUnicodeString` at `0x18008eef7`
- `ntdll!RtlFreeUnicodeString` at `0x18008ef0d`
- `ntdll!RtlFreeUnicodeString` at `0x18008ed53`
- `ntdll!RtlFreeUnicodeString` at `0x18008ed69`
- `ntdll!RtlFreeUnicodeString` at `0x18008eef7`
- `ntdll!RtlFreeUnicodeString` at `0x18008ef0d`

## pseudocode

```c

```

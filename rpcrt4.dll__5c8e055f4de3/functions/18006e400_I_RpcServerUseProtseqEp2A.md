# I_RpcServerUseProtseqEp2A

- ea: `0x18006e400`
- end: `0x18006e68c`
- name: `I_RpcServerUseProtseqEp2A`
- size: `652`
- prototype: `RPC_STATUS __stdcall(RPC_CSTR NetworkAddress, RPC_CSTR Protseq, unsigned int MaxCalls, RPC_CSTR Endpoint, void *SecurityDescriptor, void *Policy)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006e3a0`
- `0x1800a9ed0`
- `0x1800a9f90`
- `0x1800b5ea0`

## callees

- `0x18002499c`
- `0x18005ceb0`
- `0x18006d140`
- `0x18006e400`
- `0x180095650`
- `0x180097c3c`
- `0x1800a6a40`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `KERNELBASE!lstrlenA` at `0x18006e493`
- `KERNELBASE!lstrlenA` at `0x18006e493`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18006e58f`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18006e5cc`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18006e58f`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18006e5cc`
- `ntdll!RtlInitAnsiString` at `0x18006e57e`
- `ntdll!RtlInitAnsiString` at `0x18006e5bb`
- `ntdll!RtlInitAnsiString` at `0x18006e57e`
- `ntdll!RtlInitAnsiString` at `0x18006e5bb`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18006e560`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18006e560`
- `ntdll!RtlFreeUnicodeString` at `0x18006e473`
- `ntdll!RtlFreeUnicodeString` at `0x18006e483`
- `ntdll!RtlFreeUnicodeString` at `0x18006e63a`
- `ntdll!RtlFreeUnicodeString` at `0x18006e64a`
- `ntdll!RtlFreeUnicodeString` at `0x18006e473`
- `ntdll!RtlFreeUnicodeString` at `0x18006e483`
- `ntdll!RtlFreeUnicodeString` at `0x18006e63a`
- `ntdll!RtlFreeUnicodeString` at `0x18006e64a`

## pseudocode

```c

```

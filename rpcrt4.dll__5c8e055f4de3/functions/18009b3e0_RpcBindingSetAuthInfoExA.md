# RpcBindingSetAuthInfoExA

- ea: `0x18009b3e0`
- end: `0x18009b4ed`
- name: `RpcBindingSetAuthInfoExA`
- size: `269`
- prototype: `RPC_STATUS __stdcall(RPC_BINDING_HANDLE Binding, RPC_CSTR ServerPrincName, unsigned int AuthnLevel, unsigned int AuthnSvc, RPC_AUTH_IDENTITY_HANDLE AuthIdentity, unsigned int AuthzSvc, RPC_SECURITY_QOS *SecurityQos)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009b3b0`

## callees

- `0x180067e00`
- `0x180095650`
- `0x18009b3e0`
- `0x18009b4f4`
- `0x18009d6d0`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x18009b444`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18009b444`
- `ntdll!RtlInitAnsiString` at `0x18009b433`
- `ntdll!RtlInitAnsiString` at `0x18009b433`
- `ntdll!RtlFreeUnicodeString` at `0x18009b45f`
- `ntdll!RtlFreeUnicodeString` at `0x18009b4d5`
- `ntdll!RtlFreeUnicodeString` at `0x18009b45f`
- `ntdll!RtlFreeUnicodeString` at `0x18009b4d5`

## pseudocode

```c

```

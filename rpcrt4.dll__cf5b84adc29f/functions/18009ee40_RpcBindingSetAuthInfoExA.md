# RpcBindingSetAuthInfoExA

- ea: `0x18009ee40`
- end: `0x18009ef40`
- name: `RpcBindingSetAuthInfoExA`
- size: `256`
- prototype: `RPC_STATUS __stdcall(RPC_BINDING_HANDLE Binding, RPC_CSTR ServerPrincName, unsigned int AuthnLevel, unsigned int AuthnSvc, RPC_AUTH_IDENTITY_HANDLE AuthIdentity, unsigned int AuthzSvc, RPC_SECURITY_QOS *SecurityQos)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009ee10`

## callees

- `0x180008190`
- `0x18000cb1c`
- `0x180098ba0`
- `0x18009ee40`
- `0x18009ef48`
- `0x1800a100c`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18009eea5`
- `ntdll!RtlFreeUnicodeString` at `0x18009ef21`
- `ntdll!RtlFreeUnicodeString` at `0x18009eea5`
- `ntdll!RtlFreeUnicodeString` at `0x18009ef21`

## pseudocode

```c

```

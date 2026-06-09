# CSecurityUtils::GetAuthenticationPackageId(ulong *)

- ea: `0x180063ea8`
- end: `0x180063f7e`
- name: `?GetAuthenticationPackageId@CSecurityUtils@@SAJPEAK@Z`
- size: `214`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800640d0`
- `0x180064150`
- `0x180064370`

## callees

- `0x18000a210`
- `0x180063ea8`

## import_xrefs

- `ntdll!RtlInitString` at `0x180063f22`
- `ntdll!RtlInitString` at `0x180063f22`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180063f39`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x180063f39`
- `SspiCli!LsaConnectUntrusted` at `0x180063ee9`
- `SspiCli!LsaConnectUntrusted` at `0x180063ee9`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180063f6b`
- `SspiCli!LsaDeregisterLogonProcess` at `0x180063f6b`

## string_xrefs

- `0x180063f03`: `CSecurityUtils::GetAuthenticationPackageId`

## pseudocode

```c

```

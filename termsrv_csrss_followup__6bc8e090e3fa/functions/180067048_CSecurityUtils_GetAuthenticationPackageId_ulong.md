# CSecurityUtils::GetAuthenticationPackageId(ulong *)

- ea: `0x180067048`
- end: `0x180067137`
- name: `?GetAuthenticationPackageId@CSecurityUtils@@SAJPEAK@Z`
- size: `239`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180067290`
- `0x180067310`
- `0x180067530`

## callees

- `0x180009940`
- `0x180067048`

## import_xrefs

- `ntdll!RtlInitString` at `0x1800670c8`
- `ntdll!RtlInitString` at `0x1800670c8`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800670e5`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800670e5`
- `SspiCli!LsaConnectUntrusted` at `0x180067089`
- `SspiCli!LsaConnectUntrusted` at `0x180067089`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18006711d`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18006711d`

## string_xrefs

- `0x1800670a9`: `CSecurityUtils::GetAuthenticationPackageId`

## pseudocode

```c

```

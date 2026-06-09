# SetNtlmThreadOptions(int,ulong)

- ea: `0x180035938`
- end: `0x180035a68`
- name: `?SetNtlmThreadOptions@@YAJHK@Z`
- size: `304`
- prototype: `__int64 __fastcall(int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180041048`
- `0x180094ff4`
- `0x1800c89f0`
- `0x1800d40bc`

## callees

- `0x180035938`
- `0x1800de450`

## import_xrefs

- `ntdll!RtlInitString` at `0x18003598e`
- `ntdll!RtlInitString` at `0x1800359ed`
- `ntdll!RtlInitString` at `0x18003598e`
- `ntdll!RtlInitString` at `0x1800359ed`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180035a50`
- `SspiCli!LsaCallAuthenticationPackage` at `0x180035a50`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800359ff`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1800359ff`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800359c2`
- `SspiCli!LsaDeregisterLogonProcess` at `0x1800359c2`
- `SspiCli!LsaFreeReturnBuffer` at `0x180035a5d`
- `SspiCli!LsaFreeReturnBuffer` at `0x180035a5d`
- `SspiCli!LsaRegisterLogonProcess` at `0x1800359a0`
- `SspiCli!LsaRegisterLogonProcess` at `0x1800359a0`

## pseudocode

```c

```

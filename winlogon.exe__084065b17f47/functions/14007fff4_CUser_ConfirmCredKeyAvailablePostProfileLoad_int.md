# CUser::ConfirmCredKeyAvailablePostProfileLoad(int *)

- ea: `0x14007fff4`
- end: `0x1400801c3`
- name: `?ConfirmCredKeyAvailablePostProfileLoad@CUser@@QEAAJPEAH@Z`
- size: `463`
- prototype: `__int64 __fastcall(CUser *__hidden this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140047370`

## callees

- `0x14000aa04`
- `0x140032550`
- `0x140053720`
- `0x140065920`
- `0x14007fe90`
- `0x14007feb0`
- `0x14007fff4`

## import_xrefs

- `ntdll!RtlInitString` at `0x140080091`
- `ntdll!RtlInitString` at `0x140080091`
- `SspiCli!LsaCallAuthenticationPackage` at `0x140080127`
- `SspiCli!LsaCallAuthenticationPackage` at `0x140080127`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1400800aa`
- `SspiCli!LsaLookupAuthenticationPackage` at `0x1400800aa`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x140080037`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x140080037`

## string_xrefs

- `0x140080169`: `clientcore\ds\security\umstartup\winlogon\core\userobj.cxx`

## pseudocode

```c

```

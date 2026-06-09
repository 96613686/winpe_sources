# CUserName::InitializeInternetName(void)

- ea: `0x18005acdc`
- end: `0x18005afe3`
- name: `?InitializeInternetName@CUserName@@AEAAJXZ`
- size: `775`
- prototype: `__int64 __fastcall(CUserName *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18005a870`
- `0x18005a950`
- `0x18005b130`

## callees

- `0x1800013a4`
- `0x180003f30`
- `0x180004e00`
- `0x1800178e0`
- `0x18001a2a4`
- `0x18002017c`
- `0x180021db8`
- `0x18005acdc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005ad9c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005ad9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005afc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005afc1`
- `DSROLE!DsRoleFreeMemory` at `0x18005afd0`
- `DSROLE!DsRoleFreeMemory` at `0x18005afd0`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18005adc0`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18005adc0`
- `samcli!NetUserGetInfo` at `0x18005ae72`
- `samcli!NetUserGetInfo` at `0x18005ae72`

## string_xrefs

- `0x18005af1a`: `StringCchCopy failed: 0x%x in %s`
- `0x18005ad19`: `No token`
- `0x18005ad85`: `CUtils::GetComputerName failed: 0x%x in %s`

## pseudocode

```c

```

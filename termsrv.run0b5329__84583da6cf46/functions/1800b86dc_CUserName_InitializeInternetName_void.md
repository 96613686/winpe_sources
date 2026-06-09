# CUserName::InitializeInternetName(void)

- ea: `0x1800b86dc`
- end: `0x1800b89f1`
- name: `?InitializeInternetName@CUserName@@AEAAJXZ`
- size: `789`
- prototype: `__int64 __fastcall(CUserName *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800b8390`
- `0x1800b8470`
- `0x1800b8b40`

## callees

- `0x1800052d0`
- `0x18000a210`
- `0x1800127b0`
- `0x180014a2c`
- `0x180025ddc`
- `0x1800326dc`
- `0x18009d1d0`
- `0x1800b86dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b87aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b87aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b89cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b89cf`
- `samcli!NetUserGetInfo` at `0x1800b8880`
- `samcli!NetUserGetInfo` at `0x1800b8880`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800b87ce`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800b87ce`
- `DSROLE!DsRoleFreeMemory` at `0x1800b89de`
- `DSROLE!DsRoleFreeMemory` at `0x1800b89de`

## string_xrefs

- `0x1800b8928`: `StringCchCopy failed: 0x%x in %s`
- `0x1800b8793`: `CUtils::GetComputerName failed: 0x%x in %s`
- `0x1800b8719`: `No token`

## pseudocode

```c

```

# CUserName::InitializeInternetName(void)

- ea: `0x1800befa4`
- end: `0x1800bf2d8`
- name: `?InitializeInternetName@CUserName@@AEAAJXZ`
- size: `820`
- prototype: `__int64 __fastcall(CUserName *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800bec10`
- `0x1800bed00`
- `0x1800bf440`

## callees

- `0x180005314`
- `0x180009940`
- `0x180012d10`
- `0x180015044`
- `0x1800272cc`
- `0x18003444c`
- `0x1800a1c40`
- `0x1800befa4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bf072`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800bf072`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bf2a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bf2a9`
- `samcli!NetUserGetInfo` at `0x1800bf154`
- `samcli!NetUserGetInfo` at `0x1800bf154`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800bf09c`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x1800bf09c`
- `DSROLE!DsRoleFreeMemory` at `0x1800bf2be`
- `DSROLE!DsRoleFreeMemory` at `0x1800bf2be`

## string_xrefs

- `0x1800bf202`: `StringCchCopy failed: 0x%x in %s`
- `0x1800bf05b`: `CUtils::GetComputerName failed: 0x%x in %s`
- `0x1800befe1`: `No token`

## pseudocode

```c

```

# ClusterADLdap::LDAPBindToDC(ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,wchar_t const *,wchar_t const *,std::function<void (bool,bool,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)>)

- ea: `0x180099dd8`
- end: `0x18009a236`
- name: `?LDAPBindToDC@ClusterADLdap@@QEAAJKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0PEB_W1V?$function@$$A6AX_N0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z@3@@Z`
- size: `1118`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800620cc`
- `0x180065fb8`
- `0x180067238`
- `0x180067a9c`
- `0x180067e54`

## callees

- `0x180002ad0`
- `0x180005fdc`
- `0x18000aa10`
- `0x18000db2c`
- `0x18000e14c`
- `0x180099708`
- `0x18009977c`
- `0x180099dd8`
- `0x18009abe0`
- `0x1800ab010`

## import_xrefs

- `NETAPI32!DsGetDcNameW` at `0x18009a004`
- `NETAPI32!DsGetDcNameW` at `0x18009a004`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180099e89`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180099e89`
- `DSROLE!DsRoleFreeMemory` at `0x180099ebb`
- `DSROLE!DsRoleFreeMemory` at `0x180099f42`
- `DSROLE!DsRoleFreeMemory` at `0x180099f8b`
- `DSROLE!DsRoleFreeMemory` at `0x180099ebb`
- `DSROLE!DsRoleFreeMemory` at `0x180099f42`
- `DSROLE!DsRoleFreeMemory` at `0x180099f8b`
- `NTDSAPI!DsBindWithCredW` at `0x18009a14c`
- `NTDSAPI!DsBindWithCredW` at `0x18009a14c`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x18009a178`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x18009a1a2`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x18009a178`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x18009a1a2`

## string_xrefs

- `0x180099f9d`: `Attempting DsGetDcName`

## pseudocode

```c

```

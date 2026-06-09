# ClusterADLdap::LDAPBindToDC(ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,wchar_t const *,wchar_t const *,std::function<void (bool,bool,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)>)

- ea: `0x180097aa4`
- end: `0x180097ed1`
- name: `?LDAPBindToDC@ClusterADLdap@@QEAAJKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0PEB_W1V?$function@$$A6AX_N0AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z@3@@Z`
- size: `1069`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180060e9c`
- `0x180064cf4`
- `0x180065f54`
- `0x1800667cc`
- `0x180066b84`

## callees

- `0x180002a70`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000d794`
- `0x18000dd74`
- `0x180097458`
- `0x1800974c4`
- `0x180097aa4`
- `0x180098818`
- `0x1800a9010`

## import_xrefs

- `NETAPI32!DsGetDcNameW` at `0x180097cb8`
- `NETAPI32!DsGetDcNameW` at `0x180097cb8`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180097b55`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180097b55`
- `DSROLE!DsRoleFreeMemory` at `0x180097b81`
- `DSROLE!DsRoleFreeMemory` at `0x180097c02`
- `DSROLE!DsRoleFreeMemory` at `0x180097c45`
- `DSROLE!DsRoleFreeMemory` at `0x180097b81`
- `DSROLE!DsRoleFreeMemory` at `0x180097c02`
- `DSROLE!DsRoleFreeMemory` at `0x180097c45`
- `NTDSAPI!DsBindWithCredW` at `0x180097dfa`
- `NTDSAPI!DsBindWithCredW` at `0x180097dfa`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x180097e20`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x180097e44`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x180097e20`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreePasswordCredentials` at `0x180097e44`

## string_xrefs

- `0x180097c51`: `Attempting DsGetDcName`

## pseudocode

```c

```

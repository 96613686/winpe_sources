# ClusterADLdap::GetSidForCreds(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,wchar_t const *)

- ea: `0x1800977f8`
- end: `0x180097a39`
- name: `?GetSidForCreds@ClusterADLdap@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@PEB_W@Z`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180060e9c`

## callees

- `0x180002a70`
- `0x180005e68`
- `0x18000a6dc`
- `0x18000dd74`
- `0x180010708`
- `0x18009732c`
- `0x18009774c`
- `0x1800977f8`
- `0x180098224`

## import_xrefs

- `NETAPI32!NetApiBufferFree` at `0x180097932`
- `NETAPI32!NetApiBufferFree` at `0x1800979cb`
- `NETAPI32!NetApiBufferFree` at `0x180097a19`
- `NETAPI32!NetApiBufferFree` at `0x180097932`
- `NETAPI32!NetApiBufferFree` at `0x1800979cb`
- `NETAPI32!NetApiBufferFree` at `0x180097a19`
- `NETAPI32!DsGetDcNameW` at `0x18009784c`
- `NETAPI32!DsGetDcNameW` at `0x18009784c`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180097922`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x1800979bb`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180097a09`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180097922`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x1800979bb`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsFreeNameResultW` at `0x180097a09`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x1800978e9`
- `api-ms-win-security-activedirectoryclient-l1-1-0!DsCrackNamesW` at `0x1800978e9`

## pseudocode

```c

```

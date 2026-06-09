# Microsoft::Diagnostics::Utils::Os::EnumerateServicesInProcess(ulong,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &)

- ea: `0x180081c84`
- end: `0x180082424`
- name: `?EnumerateServicesInProcess@Os@Utils@Diagnostics@Microsoft@@SAJKAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z`
- size: `1952`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800e4430`

## callees

- `0x18001d160`
- `0x180026ecc`
- `0x18004a750`
- `0x18004ab70`
- `0x18007fae8`
- `0x1800807c8`
- `0x180080d94`
- `0x180081c84`
- `0x180086c3c`
- `0x180086e78`
- `0x180087044`
- `0x180089d50`
- `0x1800b2ccc`
- `0x180112c8c`
- `0x18012de40`
- `0x1801cd790`
- `0x180346010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x180081e68`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x180081e68`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180081cd1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180081cd1`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180081dd6`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180081dd6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800822c5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800822c5`
- `OLEAUT32!__imp_SysStringLen` at `0x1800822f1`
- `OLEAUT32!__imp_SysStringLen` at `0x1800822f1`
- `OLEAUT32!__imp_VariantInit` at `0x180082294`
- `OLEAUT32!__imp_VariantInit` at `0x180082294`
- `OLEAUT32!__imp_VariantClear` at `0x1800821e1`
- `OLEAUT32!__imp_VariantClear` at `0x180082341`
- `OLEAUT32!__imp_VariantClear` at `0x18008238a`
- `OLEAUT32!__imp_VariantClear` at `0x1800821e1`
- `OLEAUT32!__imp_VariantClear` at `0x180082341`
- `OLEAUT32!__imp_VariantClear` at `0x18008238a`

## string_xrefs

- `0x180081e4f`: `SELECT Name FROM Win32_Service WHERE ProcessId = `

## pseudocode

```c

```

# std::variant<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,wil::com_ptr_t<IUnknown,wil::err_exception_policy>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>>>::operator=(std::variant<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,wil::com_ptr_t<IUnknown,wil::err_exception_policy>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,int (*)(unsigned __int64),&closesocket(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,unsigned __int64>>>> &&)

- ea: `0x1400dc96c`
- end: `0x1400dcb08`
- name: `??4?$variant@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@2@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@2@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AH_K@Z$1?closesocket@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0_K@details@wil@@@details@wil@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400dc590`

## callees

- `0x1400dc96c`
- `0x1400dd6b0`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400dc9d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400dcacb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400dc9d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400dcacb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400dc9c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400dca6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400dcab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400dc9c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400dca6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400dcab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400dca7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400dcac3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400dca7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400dcac3`
- `WS2_32!__imp_closesocket` at `0x1400dc9cc`
- `WS2_32!__imp_closesocket` at `0x1400dc9cc`

## pseudocode

```c

```

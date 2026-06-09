# RpsTicketService::DecryptTicket(IMemObj *,wchar_t const * const,ulong const &,uchar const * const,ulong const &,uchar const * const,uchar const * const,IFedAuthTicket * *,ELoginFailedState &)

- ea: `0x10156f540`
- end: `0x1015701db`
- name: `?DecryptTicket@RpsTicketService@@SAJPEAVIMemObj@@QEB_WAEBKQEBE233PEAPEAVIFedAuthTicket@@AEAW4ELoginFailedState@@@Z`
- size: `3227`
- prototype: `static int(struct IMemObj *, const wchar_t *const, const unsigned int *, const unsigned __int8 *const, const unsigned int *, const unsigned __int8 *const, const unsigned __int8 *const, struct IFedAuthTicket **, enum ELoginFailedState *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x10155c720`

## callees

- `0x100401070`
- `0x100401433`
- `0x1004022e0`
- `0x100403080`
- `0x1004076a0`
- `0x10041154d`
- `0x100430d60`
- `0x10083a060`
- `0x10156f540`
- `0x101e890c0`

## import_xrefs

- `ole32!CoInitializeEx` at `0x10156f71a`
- `ole32!CoInitializeEx` at `0x10156f71a`
- `ole32!CoCreateInstance` at `0x10156f7ec`
- `ole32!CoCreateInstance` at `0x10156f7ec`
- `ole32!CLSIDFromProgID` at `0x10156f7b7`
- `ole32!CLSIDFromProgID` at `0x10156f7b7`
- `ole32!CoUninitialize` at `0x1015700b6`
- `ole32!CoUninitialize` at `0x1015700b6`
- `OLEAUT32!__imp_SysAllocString` at `0x10156fb1a`
- `OLEAUT32!__imp_SysAllocString` at `0x10156fb2b`
- `OLEAUT32!__imp_SysAllocString` at `0x10156fbe5`
- `OLEAUT32!__imp_SysAllocString` at `0x10156fda4`
- `OLEAUT32!__imp_SysAllocString` at `0x10156fe97`
- `OLEAUT32!__imp_SysAllocString` at `0x10156fefe`
- `OLEAUT32!__imp_SysAllocString` at `0x10156fb1a`
- `OLEAUT32!__imp_SysAllocString` at `0x10156fb2b`
- `OLEAUT32!__imp_SysAllocString` at `0x10156fbe5`
- `OLEAUT32!__imp_SysAllocString` at `0x10156fda4`
- `OLEAUT32!__imp_SysAllocString` at `0x10156fe97`
- `OLEAUT32!__imp_SysAllocString` at `0x10156fefe`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x10156f97d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x10156f9e1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x10156fab4`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x10156f97d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x10156f9e1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x10156fab4`
- `OLEAUT32!__imp_SysFreeString` at `0x10156f9b2`
- `OLEAUT32!__imp_SysFreeString` at `0x10156f9c5`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fa07`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fae8`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fafa`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fb81`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fb93`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fc20`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fc32`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fddf`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fdf1`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fed2`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fee4`
- `OLEAUT32!__imp_SysFreeString` at `0x10156ff49`
- `OLEAUT32!__imp_SysFreeString` at `0x10156ff5b`
- `OLEAUT32!__imp_SysFreeString` at `0x10156f9b2`
- `OLEAUT32!__imp_SysFreeString` at `0x10156f9c5`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fa07`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fae8`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fafa`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fb81`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fb93`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fc20`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fc32`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fddf`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fdf1`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fed2`
- `OLEAUT32!__imp_SysFreeString` at `0x10156fee4`
- `OLEAUT32!__imp_SysFreeString` at `0x10156ff49`
- `OLEAUT32!__imp_SysFreeString` at `0x10156ff5b`
- `OLEAUT32!__imp_SysStringLen` at `0x10156f96e`
- `OLEAUT32!__imp_SysStringLen` at `0x10156f9d2`
- `OLEAUT32!__imp_SysStringLen` at `0x10156faa5`
- `OLEAUT32!__imp_SysStringLen` at `0x10156f96e`
- `OLEAUT32!__imp_SysStringLen` at `0x10156f9d2`
- `OLEAUT32!__imp_SysStringLen` at `0x10156faa5`
- `OLEAUT32!__imp_VariantInit` at `0x10156fb04`
- `OLEAUT32!__imp_VariantInit` at `0x10156fbd8`
- `OLEAUT32!__imp_VariantInit` at `0x10156fd97`
- `OLEAUT32!__imp_VariantInit` at `0x10156fe8a`
- `OLEAUT32!__imp_VariantInit` at `0x10156fef1`
- `OLEAUT32!__imp_VariantInit` at `0x10156fb04`
- `OLEAUT32!__imp_VariantInit` at `0x10156fbd8`
- `OLEAUT32!__imp_VariantInit` at `0x10156fd97`
- `OLEAUT32!__imp_VariantInit` at `0x10156fe8a`
- `OLEAUT32!__imp_VariantInit` at `0x10156fef1`
- `OLEAUT32!__imp_VariantClear` at `0x10156fb70`
- `OLEAUT32!__imp_VariantClear` at `0x10156fbba`
- `OLEAUT32!__imp_VariantClear` at `0x10156fc0f`
- `OLEAUT32!__imp_VariantClear` at `0x10156fc9d`
- `OLEAUT32!__imp_VariantClear` at `0x10156fdce`
- `OLEAUT32!__imp_VariantClear` at `0x10156fe80`
- `OLEAUT32!__imp_VariantClear` at `0x10156fec1`
- `OLEAUT32!__imp_VariantClear` at `0x10156ff2b`
- `OLEAUT32!__imp_VariantClear` at `0x10156ff38`
- `OLEAUT32!__imp_VariantClear` at `0x101570075`
- `OLEAUT32!__imp_VariantClear` at `0x101570082`
- `OLEAUT32!__imp_VariantClear` at `0x10156fb70`
- `OLEAUT32!__imp_VariantClear` at `0x10156fbba`
- `OLEAUT32!__imp_VariantClear` at `0x10156fc0f`
- `OLEAUT32!__imp_VariantClear` at `0x10156fc9d`
- `OLEAUT32!__imp_VariantClear` at `0x10156fdce`
- `OLEAUT32!__imp_VariantClear` at `0x10156fe80`
- `OLEAUT32!__imp_VariantClear` at `0x10156fec1`
- `OLEAUT32!__imp_VariantClear` at `0x10156ff2b`
- `OLEAUT32!__imp_VariantClear` at `0x10156ff38`
- `OLEAUT32!__imp_VariantClear` at `0x101570075`
- `OLEAUT32!__imp_VariantClear` at `0x101570082`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10156fa0d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10156fcc5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10157000d`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10156fcc5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10157000d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10156f89a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10156fc69`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10156fe46`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10156ff8b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10156f89a`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10156fc69`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10156fe46`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x10156ff8b`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10156f67f`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x10156f67f`
- `sqldk!SystemThread_TlsIndex` at `0x10156f63d`
- `sqldk!SystemThread_TlsIndex` at `0x10156f697`
- `sqldk!SystemThread_TlsOffset` at `0x10156f646`
- `sqldk!SystemThread_TlsOffset` at `0x10156f6a0`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10156f65f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10156f6bb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10156f65f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10156f6bb`
- `sqldk!??_V@YAXPEAX@Z` at `0x10156f8ae`
- `sqldk!??_V@YAXPEAX@Z` at `0x10156fa56`
- `sqldk!??_V@YAXPEAX@Z` at `0x10156fc7d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10156fe5a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10156ff9b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015700a8`
- `sqldk!??_V@YAXPEAX@Z` at `0x10157016c`
- `sqldk!??_V@YAXPEAX@Z` at `0x101570176`
- `sqldk!??_V@YAXPEAX@Z` at `0x101570181`
- `sqldk!??_V@YAXPEAX@Z` at `0x10157019d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015701a9`
- `sqldk!??_V@YAXPEAX@Z` at `0x10156f8ae`
- `sqldk!??_V@YAXPEAX@Z` at `0x10156fa56`
- `sqldk!??_V@YAXPEAX@Z` at `0x10156fc7d`
- `sqldk!??_V@YAXPEAX@Z` at `0x10156fe5a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10156ff9b`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015700a8`
- `sqldk!??_V@YAXPEAX@Z` at `0x10157016c`
- `sqldk!??_V@YAXPEAX@Z` at `0x101570176`
- `sqldk!??_V@YAXPEAX@Z` at `0x101570181`
- `sqldk!??_V@YAXPEAX@Z` at `0x10157019d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015701a9`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10156f92a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10156f93d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10156f92a`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10156f93d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10156f949`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x10156f949`

## string_xrefs

- `0x10156f890`: `sql\ntdbms\msql\security\src\RpsTicketService.cpp`
- `0x10156fc5d`: `sql\ntdbms\msql\security\src\RpsTicketService.cpp`
- `0x10156fcb6`: `sql\ntdbms\msql\security\src\RpsTicketService.cpp`
- `0x10156fe37`: `sql\ntdbms\msql\security\src\RpsTicketService.cpp`
- `0x10156ff7a`: `sql\ntdbms\msql\security\src\RpsTicketService.cpp`
- `0x10156fffc`: `sql\ntdbms\msql\security\src\RpsTicketService.cpp`

## pseudocode

```c

```

# SpPolybaseLeaveGroup(CCompExecCtxt const &,CSpecProcRuntimeParams const * const,CParamExchange * const,CXVariant * const)

- ea: `0x101230790`
- end: `0x101231067`
- name: `?SpPolybaseLeaveGroup@@YAXAEBVCCompExecCtxt@@QEBVCSpecProcRuntimeParams@@QEAVCParamExchange@@QEAVCXVariant@@@Z`
- size: `2263`
- prototype: `void __fastcall(const struct CCompExecCtxt *, const struct CSpecProcRuntimeParams *const, struct CParamExchange *const, struct CXVariant *const)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x100401070`
- `0x100401090`
- `0x1004132a0`
- `0x100430960`
- `0x1005511a0`
- `0x10055a5d0`
- `0x1007d8d30`
- `0x101230790`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x101230ea8`
- `KERNEL32!lstrcmpiW` at `0x101230ea8`
- `ADVAPI32!RegQueryValueExW` at `0x101230ac5`
- `ADVAPI32!RegQueryValueExW` at `0x101230bce`
- `ADVAPI32!RegQueryValueExW` at `0x101230d7b`
- `ADVAPI32!RegQueryValueExW` at `0x101230ac5`
- `ADVAPI32!RegQueryValueExW` at `0x101230bce`
- `ADVAPI32!RegQueryValueExW` at `0x101230d7b`
- `ADVAPI32!RegOpenKeyExW` at `0x101230a83`
- `ADVAPI32!RegOpenKeyExW` at `0x101230f3d`
- `ADVAPI32!RegOpenKeyExW` at `0x101230a83`
- `ADVAPI32!RegOpenKeyExW` at `0x101230f3d`
- `ADVAPI32!RegSetValueExW` at `0x101230bf8`
- `ADVAPI32!RegSetValueExW` at `0x101230cff`
- `ADVAPI32!RegSetValueExW` at `0x101230dac`
- `ADVAPI32!RegSetValueExW` at `0x101230f7b`
- `ADVAPI32!RegSetValueExW` at `0x101230bf8`
- `ADVAPI32!RegSetValueExW` at `0x101230cff`
- `ADVAPI32!RegSetValueExW` at `0x101230dac`
- `ADVAPI32!RegSetValueExW` at `0x101230f7b`
- `ADVAPI32!RegCloseKey` at `0x101230afa`
- `ADVAPI32!RegCloseKey` at `0x101230c08`
- `ADVAPI32!RegCloseKey` at `0x101230c2e`
- `ADVAPI32!RegCloseKey` at `0x101230c92`
- `ADVAPI32!RegCloseKey` at `0x101230d0f`
- `ADVAPI32!RegCloseKey` at `0x101230dbc`
- `ADVAPI32!RegCloseKey` at `0x101230de2`
- `ADVAPI32!RegCloseKey` at `0x101230e2d`
- `ADVAPI32!RegCloseKey` at `0x101230f8b`
- `ADVAPI32!RegCloseKey` at `0x101230fd4`
- `ADVAPI32!RegCloseKey` at `0x101230afa`
- `ADVAPI32!RegCloseKey` at `0x101230c08`
- `ADVAPI32!RegCloseKey` at `0x101230c2e`
- `ADVAPI32!RegCloseKey` at `0x101230c92`
- `ADVAPI32!RegCloseKey` at `0x101230d0f`
- `ADVAPI32!RegCloseKey` at `0x101230dbc`
- `ADVAPI32!RegCloseKey` at `0x101230de2`
- `ADVAPI32!RegCloseKey` at `0x101230e2d`
- `ADVAPI32!RegCloseKey` at `0x101230f8b`
- `ADVAPI32!RegCloseKey` at `0x101230fd4`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101230e8b`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101230edd`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x10123088a`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x1012308bb`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101230e76`
- `sqldk!?GetOperatingSystemName@OsInfo@@QEBAQEB_WXZ` at `0x1012308c2`
- `sqldk!?GetOperatingSystemName@OsInfo@@QEBAQEB_WXZ` at `0x1012308c2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101230a39`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101230eb2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101230ef3`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101230a39`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101230eb2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101230ef3`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230b13`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230c21`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230c47`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230cab`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230d28`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230dd5`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230dfb`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230e4f`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230fa4`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230ff0`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230b13`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230c21`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230c47`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230cab`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230d28`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230dd5`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230dfb`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230e4f`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230fa4`
- `sqldk!?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z` at `0x101230ff0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10123082b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230884`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10123090d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012309c0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230aee`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230b39`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230c6f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230cd1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230d4e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230e23`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230e70`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230fca`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101231011`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10123082b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230884`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10123090d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x1012309c0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230aee`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230b39`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230c6f`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230cd1`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230d4e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230e23`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230e70`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101230fca`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101231011`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101230a1e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101230b97`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101230a1e`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101230b97`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x101230891`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x101230e7d`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x101230891`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x101230e7d`
- `sqldk!SystemThread_TlsIndex` at `0x1012309cf`
- `sqldk!SystemThread_TlsIndex` at `0x101230b48`
- `sqldk!SystemThread_TlsOffset` at `0x1012309d8`
- `sqldk!SystemThread_TlsOffset` at `0x101230b51`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1012309f3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101230b6c`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1012309f3`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101230b6c`
- `sqldk!??_V@YAXPEAX@Z` at `0x101230e37`
- `sqldk!??_V@YAXPEAX@Z` at `0x101231031`
- `sqldk!??_V@YAXPEAX@Z` at `0x101230e37`
- `sqldk!??_V@YAXPEAX@Z` at `0x101231031`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x101230843`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x101230843`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x101230913`
- `sqlmin!?GetMasterDbId@@YAGXZ` at `0x101230913`

## string_xrefs

- `0x101230ebb`: `SYSTEM\CurrentControlSet\Services\SQLPBENGINE`
- `0x101230f01`: `SYSTEM\CurrentControlSet\Services\SQLPBENGINE`
- `0x101230a42`: `\Polybase\Configuration`

## pseudocode

```c

```

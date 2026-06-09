# AzureADGraphConnection::FetchObjectIDAndNameByOnPremSID(IMemObj *,_GUID const &,wchar_t const * const,CAutoRg<wchar_t> const &,bool const &,uchar * *,ulong &,CAutoRg<wchar_t> &,bool &,bool &,AADErrorState &,CAutoRg<wchar_t> &)

- ea: `0x101552370`
- end: `0x10155332d`
- name: `?FetchObjectIDAndNameByOnPremSID@AzureADGraphConnection@@UEAAKPEAVIMemObj@@AEBU_GUID@@QEB_WAEBV?$CAutoRg@_W@@AEB_NPEAPEAEAEAKAEAV4@AEA_N8AEAW4AADErrorState@@7@Z`
- size: `4029`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x100401070`
- `0x100401433`
- `0x100422f40`
- `0x10071db70`
- `0x10077eac0`
- `0x10154c680`
- `0x10154ebe0`
- `0x101552370`
- `0x101554170`
- `0x101554960`
- `0x1015555b0`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x101553114`
- `RPCRT4!UuidFromStringW` at `0x101553114`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101552496`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1015525df`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1015529b6`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101552496`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1015525df`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1015529b6`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101552caf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101552e63`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101553096`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101553232`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101552caf`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101552e63`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101553096`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101553232`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1015527df`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1015528f7`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10155290c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1015527df`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1015528f7`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10155290c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015525f2`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015527a1`
- `sqldk!??_V@YAXPEAX@Z` at `0x101552835`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015529c9`
- `sqldk!??_V@YAXPEAX@Z` at `0x101552b6b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101552cc3`
- `sqldk!??_V@YAXPEAX@Z` at `0x101553247`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015532b4`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015532bf`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015532cb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015532d6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015532e1`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015532eb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015532f5`
- `sqldk!??_V@YAXPEAX@Z` at `0x101553301`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015525f2`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015527a1`
- `sqldk!??_V@YAXPEAX@Z` at `0x101552835`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015529c9`
- `sqldk!??_V@YAXPEAX@Z` at `0x101552b6b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101552cc3`
- `sqldk!??_V@YAXPEAX@Z` at `0x101553247`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015532b4`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015532bf`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015532cb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015532d6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015532e1`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015532eb`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015532f5`
- `sqldk!??_V@YAXPEAX@Z` at `0x101553301`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x1015524ff`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101552d9f`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101552e0a`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101552e8b`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101552efd`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10155303d`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x1015524ff`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101552d9f`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101552e0a`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101552e8b`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101552efd`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10155303d`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10155251d`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x101552dc4`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x101552e2c`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x101552eac`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x101552f1e`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10155305f`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10155251d`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x101552dc4`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x101552e2c`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x101552eac`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x101552f1e`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10155305f`
- `VCRUNTIME140!strstr` at `0x101552886`
- `VCRUNTIME140!strstr` at `0x1015528c8`
- `VCRUNTIME140!strstr` at `0x101552bb4`
- `VCRUNTIME140!strstr` at `0x101552bf4`
- `VCRUNTIME140!strstr` at `0x101552c29`
- `VCRUNTIME140!strstr` at `0x101552f9c`
- `VCRUNTIME140!strstr` at `0x101552886`
- `VCRUNTIME140!strstr` at `0x1015528c8`
- `VCRUNTIME140!strstr` at `0x101552bb4`
- `VCRUNTIME140!strstr` at `0x101552bf4`
- `VCRUNTIME140!strstr` at `0x101552c29`
- `VCRUNTIME140!strstr` at `0x101552f9c`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10155312d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x101553167`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x10155312d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x101553167`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x101553139`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x101553173`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x101553139`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x101553173`
- `api-ms-win-crt-convert-l1-1-0!mbstowcs_s` at `0x101552ce2`
- `api-ms-win-crt-convert-l1-1-0!mbstowcs_s` at `0x101552ce2`

## string_xrefs

- `0x101553016`: `"securityEnabled":`
- `0x101552489`: `sql\ntdbms\msql\security\src\AzureActiveDirectoryService.cpp`
- `0x1015525d0`: `sql\ntdbms\msql\security\src\AzureActiveDirectoryService.cpp`
- `0x1015529a9`: `sql\ntdbms\msql\security\src\AzureActiveDirectoryService.cpp`
- `0x101552c97`: `sql\ntdbms\msql\security\src\AzureActiveDirectoryService.cpp`
- `0x101552e4f`: `sql\ntdbms\msql\security\src\AzureActiveDirectoryService.cpp`
- `0x101553082`: `sql\ntdbms\msql\security\src\AzureActiveDirectoryService.cpp`
- `0x10155321c`: `sql\ntdbms\msql\security\src\AzureActiveDirectoryService.cpp`
- `0x101552a41`: `/groups?$filter=onPremisesSecurityIdentifier eq '`
- `0x101552672`: `/users?$filter=onPremisesSecurityIdentifier eq '`
- `0x101552de3`: `"securityEnabled":`

## pseudocode

```c

```

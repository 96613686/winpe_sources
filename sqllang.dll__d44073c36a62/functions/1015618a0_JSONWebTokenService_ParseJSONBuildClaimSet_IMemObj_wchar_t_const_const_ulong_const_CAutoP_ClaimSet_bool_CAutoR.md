# JSONWebTokenService::ParseJSONBuildClaimSet(IMemObj *,wchar_t const * const,ulong const &,CAutoP<ClaimSet> &,bool &,CAutoRg<uchar> &,ulong &,JSONWebTokenErrorState &,ulong &,bool &,bool &,bool &)

- ea: `0x1015618a0`
- end: `0x101562ab8`
- name: `?ParseJSONBuildClaimSet@JSONWebTokenService@@SAJPEAVIMemObj@@QEB_WAEBKAEAV?$CAutoP@VClaimSet@@@@AEA_NAEAV?$CAutoRg@E@@AEAKAEAW4JSONWebTokenErrorState@@6444@Z`
- size: `4632`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x101554bc0`
- `0x101562ac0`
- `0x10156cd20`

## callees

- `0x100401070`
- `0x100401433`
- `0x100403080`
- `0x10040be50`
- `0x10041a970`
- `0x10054bd60`
- `0x10077eac0`
- `0x100860500`
- `0x100a81c80`
- `0x10154c2e0`
- `0x10154c590`
- `0x10154ee80`
- `0x1015618a0`
- `0x101dd32c0`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x1015620ab`
- `RPCRT4!UuidFromStringW` at `0x101562315`
- `RPCRT4!UuidFromStringW` at `0x101562766`
- `RPCRT4!UuidFromStringW` at `0x1015620ab`
- `RPCRT4!UuidFromStringW` at `0x101562315`
- `RPCRT4!UuidFromStringW` at `0x101562766`
- `SHLWAPI!StrStrIW` at `0x10156261e`
- `SHLWAPI!StrStrIW` at `0x10156261e`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101561a3b`
- `sqldk!?x_pDefAllocMemObj@@3PEAVIMemObj@@EA` at `0x101561c09`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101561b9a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101561e1c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1015624c3`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101561b9a`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101561e1c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1015624c3`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101561bd5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101561cd1`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101561bd5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101561cd1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101561c61`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101561da9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101561f50`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101562202`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10156269b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101562717`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101561c61`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101561da9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101561f50`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101562202`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10156269b`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101562717`
- `sqldk!SystemThread_TlsIndex` at `0x101561974`
- `sqldk!SystemThread_TlsIndex` at `0x101562445`
- `sqldk!SystemThread_TlsOffset` at `0x10156197d`
- `sqldk!SystemThread_TlsOffset` at `0x10156244e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101561d34`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101561e5d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101561e6e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101562382`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101562930`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10156296a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101562a5f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101562a71`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101561d34`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101561e5d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101561e6e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101562382`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101562930`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10156296a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101562a5f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x101562a71`
- `sqldk!??_V@YAXPEAX@Z` at `0x101561a86`
- `sqldk!??_V@YAXPEAX@Z` at `0x101561dc0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015627d0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015627e2`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015629a3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015629c5`
- `sqldk!??_V@YAXPEAX@Z` at `0x101562a26`
- `sqldk!??_V@YAXPEAX@Z` at `0x101562a31`
- `sqldk!??_V@YAXPEAX@Z` at `0x101561a86`
- `sqldk!??_V@YAXPEAX@Z` at `0x101561dc0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015627d0`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015627e2`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015629a3`
- `sqldk!??_V@YAXPEAX@Z` at `0x1015629c5`
- `sqldk!??_V@YAXPEAX@Z` at `0x101562a26`
- `sqldk!??_V@YAXPEAX@Z` at `0x101562a31`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101561fa3`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101561fee`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10156203e`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101562069`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101562101`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10156213e`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10156218e`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x1015623ae`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10156240d`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101562552`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x1015625ae`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10156281e`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101561fa3`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101561fee`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10156203e`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101562069`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101562101`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10156213e`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10156218e`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x1015623ae`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10156240d`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101562552`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x1015625ae`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10156281e`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x101561fc1`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10156200c`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10156205c`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x101562088`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10156211f`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10156215c`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x1015621ac`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x1015623cc`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10156242b`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x1015625cc`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10156283c`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x101561fc1`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10156200c`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10156205c`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x101562088`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10156211f`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10156215c`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x1015621ac`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x1015623cc`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10156242b`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x1015625cc`
- `sqlTsEs!?FEqIgnoreCaseW@CDefaultCollation@@QEBA_NPEB_WK0K@Z` at `0x10156283c`
- `sqlTsEs!?IHashW@CDefaultCollation@@QEBAHPEB_WH@Z` at `0x101562571`
- `sqlTsEs!?IHashW@CDefaultCollation@@QEBAHPEB_WH@Z` at `0x101562571`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x101562797`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x101562797`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1015627a3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1015627a3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x101561ebb`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x101561ebb`
- `sqlmin!GetXdbServerGlobals` at `0x101561aca`
- `sqlmin!GetXdbServerGlobals` at `0x101561b0f`
- `sqlmin!GetXdbServerGlobals` at `0x1015625e3`
- `sqlmin!GetXdbServerGlobals` at `0x101561aca`
- `sqlmin!GetXdbServerGlobals` at `0x101561b0f`
- `sqlmin!GetXdbServerGlobals` at `0x1015625e3`

## string_xrefs

- `0x101561c50`: `Sql\DkTemp\base\include\sehash.inl`
- `0x101561a5b`: `AADServerAdminSid`
- `0x101561bc6`: `sql\ntdbms\msql\security\inc\FedAuth.h`
- `0x101561cc2`: `sql\ntdbms\msql\security\inc\FedAuth.h`
- `0x101561b86`: `sql\ntdbms\msql\security\src\JSONWebTokenService.cpp`
- `0x101561d96`: `sql\ntdbms\msql\security\src\JSONWebTokenService.cpp`
- `0x101561e0b`: `sql\ntdbms\msql\security\src\JSONWebTokenService.cpp`
- `0x101561f3b`: `sql\ntdbms\msql\security\src\JSONWebTokenService.cpp`
- `0x1015621ed`: `sql\ntdbms\msql\security\src\JSONWebTokenService.cpp`
- `0x1015624a9`: `sql\ntdbms\msql\security\src\JSONWebTokenService.cpp`
- `0x101562686`: `sql\ntdbms\msql\security\src\JSONWebTokenService.cpp`
- `0x101562705`: `sql\ntdbms\msql\security\src\JSONWebTokenService.cpp`

## pseudocode

```c

```

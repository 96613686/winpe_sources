# LandingZone::RefreshSASTokenIfNeeded(SynapseLinkLogger *)

- ea: `0x10114e6c0`
- end: `0x10114f2cb`
- name: `?RefreshSASTokenIfNeeded@LandingZone@@AEAAXPEAVSynapseLinkLogger@@@Z`
- size: `3083`
- prototype: `void __fastcall(LandingZone *__hidden this, struct SynapseLinkLogger *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x10114c620`

## callees

- `0x100401490`
- `0x100402000`
- `0x10041b5d0`
- `0x1005f1f00`
- `0x100621b90`
- `0x100626050`
- `0x10072d4d0`
- `0x10072d690`
- `0x1010b5690`
- `0x101129200`
- `0x10114e6c0`
- `0x101150870`
- `0x101151a30`
- `0x1011d1ab0`
- `0x1011f2760`
- `0x101a38330`

## import_xrefs

- `WINHTTP!WinHttpConnect` at `0x10114ea54`
- `WINHTTP!WinHttpConnect` at `0x10114ea54`
- `WINHTTP!WinHttpCloseHandle` at `0x10114eb5b`
- `WINHTTP!WinHttpCloseHandle` at `0x10114eb6d`
- `WINHTTP!WinHttpCloseHandle` at `0x10114ebcb`
- `WINHTTP!WinHttpCloseHandle` at `0x10114ebdd`
- `WINHTTP!WinHttpCloseHandle` at `0x10114eb5b`
- `WINHTTP!WinHttpCloseHandle` at `0x10114eb6d`
- `WINHTTP!WinHttpCloseHandle` at `0x10114ebcb`
- `WINHTTP!WinHttpCloseHandle` at `0x10114ebdd`
- `WINHTTP!WinHttpOpen` at `0x10114e9cc`
- `WINHTTP!WinHttpOpen` at `0x10114e9cc`
- `KERNEL32!QueryPerformanceCounter` at `0x10114eebc`
- `KERNEL32!QueryPerformanceCounter` at `0x10114ef11`
- `KERNEL32!QueryPerformanceCounter` at `0x10114eebc`
- `KERNEL32!QueryPerformanceCounter` at `0x10114ef11`
- `KERNEL32!GetLastError` at `0x10114e9da`
- `KERNEL32!GetLastError` at `0x10114ea63`
- `KERNEL32!GetLastError` at `0x10114e9da`
- `KERNEL32!GetLastError` at `0x10114ea63`
- `ole32!CoTaskMemFree` at `0x10114ee41`
- `ole32!CoTaskMemFree` at `0x10114ee41`
- `ole32!StringFromCLSID` at `0x10114ede8`
- `ole32!StringFromCLSID` at `0x10114ede8`
- `sqlTsEs!?DateOrTimeFromWstr@SQLDATE@@AEAAJPEB_WJJJJFPEBVCDefaultCollation@@@Z` at `0x10114f135`
- `sqlTsEs!?DateOrTimeFromWstr@SQLDATE@@AEAAJPEB_WJJJJFPEBVCDefaultCollation@@@Z` at `0x10114f135`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10114f102`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x10114f102`
- `sqlTsEs!?DateDiff@SQLDATE@@QEBAJJPEBU1@PEAJ@Z` at `0x10114e765`
- `sqlTsEs!?DateDiff@SQLDATE@@QEBAJJPEBU1@PEAJ@Z` at `0x10114e765`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x10114ecf7`
- `sqlTsEs!?WszFromWsz@@YAPEA_WPEAVIMemObj@@PEB_WPEAH@Z` at `0x10114ecf7`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10114e837`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10114ebf4`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10114edac`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10114ee62`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10114eed0`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10114eead`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10114ef01`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10114ed59`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10114e7d6`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10114e7d6`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10114e895`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10114eca2`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10114e895`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10114eca2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114e928`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114e980`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114e9b0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114ea3b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114eac4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114efb6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114efec`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114f188`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114f214`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114f264`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114e928`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114e980`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114e9b0`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114ea3b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114eac4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114efb6`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114efec`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114f188`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114f214`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x10114f264`
- `sqldk!SystemThread_TlsIndex` at `0x10114ec07`
- `sqldk!SystemThread_TlsIndex` at `0x10114ecb7`
- `sqldk!SystemThread_TlsIndex` at `0x10114ee7f`
- `sqldk!SystemThread_TlsOffset` at `0x10114ec10`
- `sqldk!SystemThread_TlsOffset` at `0x10114ecc0`
- `sqldk!SystemThread_TlsOffset` at `0x10114ee88`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10114eb7e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10114ebee`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10114eb7e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10114ebee`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10114ec2b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10114ecd9`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10114ec2b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10114ecd9`
- `sqldk!??_V@YAXPEAX@Z` at `0x10114e98c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10114eb4c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10114ebbc`
- `sqldk!??_V@YAXPEAX@Z` at `0x10114ed0a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10114f29b`
- `sqldk!??_V@YAXPEAX@Z` at `0x10114e98c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10114eb4c`
- `sqldk!??_V@YAXPEAX@Z` at `0x10114ebbc`
- `sqldk!??_V@YAXPEAX@Z` at `0x10114ed0a`
- `sqldk!??_V@YAXPEAX@Z` at `0x10114f29b`
- `VCRUNTIME140!wcsstr` at `0x10114f000`
- `VCRUNTIME140!wcsstr` at `0x10114f047`
- `VCRUNTIME140!wcsstr` at `0x10114f0bc`
- `VCRUNTIME140!wcsstr` at `0x10114f000`
- `VCRUNTIME140!wcsstr` at `0x10114f047`
- `VCRUNTIME140!wcsstr` at `0x10114f0bc`
- `VCRUNTIME140!wcschr` at `0x10114f01e`
- `VCRUNTIME140!wcschr` at `0x10114f01e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10114edb8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10114edb8`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x10114f080`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x10114f0a1`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x10114f0e8`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x10114f080`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x10114f0a1`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x10114f0e8`

## string_xrefs

- `0x10114ec51`: `SynapseLinkBlobStorageDNSSuffix`
- `0x10114ed23`: `SynapseLinkBlobStorageDNSSuffix`
- `0x10114f286`: `Successfully retrieve the SAS token from Synapse for topic ID: `
- `0x10114e7c6`: `sql\ntdbms\srvrepl\src\SynapseLink\LandingZone.cpp`
- `0x10114ef96`: `sql\ntdbms\srvrepl\src\SynapseLink\LandingZone.cpp`
- `0x10114f1f8`: `sql\ntdbms\srvrepl\src\SynapseLink\LandingZone.cpp`
- `0x10114eb0d`: `Set table group need force drop because receive synapse workpace not found or table group(link connection) not found error from SynapseGateway response. Table group id: `
- `0x10114e78d`: `Trying to get SAS token from synapse gateway client for table group id: `
- `0x10114e80f`: `/tokenConfiguration?api-version=2021-06-01`
- `0x10114e801`: `/linkconnections/`
- `0x10114ea03`: `SynapseGatewayClient failed to create internet session with OS error code:`
- `0x10114e9c5`: `Azure Synapse Link client`
- `0x10114ec8f`: `"sql\\ntdbms\\srvrepl\\src\\SynapseLink\\LandingZone.cpp"`

## pseudocode

```c

```

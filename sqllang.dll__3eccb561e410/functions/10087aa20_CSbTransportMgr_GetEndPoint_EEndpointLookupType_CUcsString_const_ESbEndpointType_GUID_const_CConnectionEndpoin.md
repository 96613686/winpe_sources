# CSbTransportMgr::GetEndPoint(EEndpointLookupType,CUcsString const &,ESbEndpointType,_GUID const &,CConnectionEndpoint * &,EEndpointLookupResult &,CConnectionEndpoint *,bool)

- ea: `0x10087aa20`
- end: `0x10087be39`
- name: `?GetEndPoint@CSbTransportMgr@@QEAA_NW4EEndpointLookupType@@AEBUCUcsString@@W4ESbEndpointType@@AEBU_GUID@@AEAPEAVCConnectionEndpoint@@AEAW4EEndpointLookupResult@@PEAV6@_N@Z`
- size: `5145`
- prototype: ``
- caller_count: `4`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x100874bd0`
- `0x100875500`
- `0x100876080`
- `0x100877ba0`

## callees

- `0x100401070`
- `0x100401090`
- `0x100838a20`
- `0x10083a1d0`
- `0x10083a3f0`
- `0x10083a660`
- `0x10083ac70`
- `0x10083afd0`
- `0x10083b800`
- `0x10083c9a0`
- `0x100840660`
- `0x1008406e0`
- `0x100848a60`
- `0x100861920`
- `0x100862be0`
- `0x100870f80`
- `0x100878be0`
- `0x10087a7f0`
- `0x10087aa20`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x10087b159`
- `KERNEL32!QueryPerformanceCounter` at `0x10087b1b2`
- `KERNEL32!QueryPerformanceCounter` at `0x10087b4e0`
- `KERNEL32!QueryPerformanceCounter` at `0x10087b533`
- `KERNEL32!QueryPerformanceCounter` at `0x10087bb22`
- `KERNEL32!QueryPerformanceCounter` at `0x10087bb75`
- `KERNEL32!QueryPerformanceCounter` at `0x10087b159`
- `KERNEL32!QueryPerformanceCounter` at `0x10087b1b2`
- `KERNEL32!QueryPerformanceCounter` at `0x10087b4e0`
- `KERNEL32!QueryPerformanceCounter` at `0x10087b533`
- `KERNEL32!QueryPerformanceCounter` at `0x10087bb22`
- `KERNEL32!QueryPerformanceCounter` at `0x10087bb75`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x10087b08a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x10087b6a8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x10087b08a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x10087b6a8`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10087b170`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10087b4f4`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x10087bb36`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10087b0f9`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10087b486`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10087bac5`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10087b214`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10087b591`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10087b6f9`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10087b982`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10087bcce`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10087bde1`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10087b147`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10087b1a2`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10087b4d1`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10087b523`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10087bb13`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10087bb65`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10087ada2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10087add2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10087ada2`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x10087add2`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10087afb1`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10087b037`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10087b29f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10087b374`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10087b415`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10087afb1`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10087b037`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10087b29f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10087b374`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x10087b415`
- `sqldk!SystemThread_TlsIndex` at `0x10087b119`
- `sqldk!SystemThread_TlsIndex` at `0x10087b4a3`
- `sqldk!SystemThread_TlsIndex` at `0x10087bae5`
- `sqldk!SystemThread_TlsOffset` at `0x10087b122`
- `sqldk!SystemThread_TlsOffset` at `0x10087b4ac`
- `sqldk!SystemThread_TlsOffset` at `0x10087baee`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087abc1`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087aca1`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087aff4`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087b5d8`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087b5f5`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087b603`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087b62f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087b63d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087b64d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087ba17`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087ba77`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087ba85`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087bdb2`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087bdc1`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087bdd1`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087abc1`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087aca1`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087aff4`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087b5d8`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087b5f5`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087b603`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087b62f`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087b63d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087b64d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087ba17`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087ba77`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087ba85`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087bdb2`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087bdc1`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10087bdd1`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x10087adc8`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x10087adeb`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x10087adc8`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x10087adeb`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10087ac00`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10087ac2c`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10087ac7a`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10087ad1d`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10087ac00`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10087ac2c`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10087ac7a`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x10087ad1d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10087b220`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10087b59d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10087b705`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10087b98e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10087bcda`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10087bded`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10087b220`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10087b59d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10087b705`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10087b98e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10087bcda`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10087bded`

## string_xrefs

- `0x10087afa1`: `sql\common\dk\ucs\src\ucstransportmgr.cpp`
- `0x10087b027`: `sql\common\dk\ucs\src\ucstransportmgr.cpp`
- `0x10087b28d`: `sql\common\dk\ucs\src\ucstransportmgr.cpp`
- `0x10087b360`: `sql\common\dk\ucs\src\ucstransportmgr.cpp`
- `0x10087b406`: `sql\common\dk\ucs\src\ucstransportmgr.cpp`

## pseudocode

```c

```

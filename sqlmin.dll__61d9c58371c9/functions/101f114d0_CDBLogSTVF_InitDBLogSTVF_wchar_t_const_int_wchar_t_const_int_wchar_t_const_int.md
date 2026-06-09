# CDBLogSTVF::InitDBLogSTVF(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)

- ea: `0x101f114d0`
- end: `0x101f126c1`
- name: `?InitDBLogSTVF@CDBLogSTVF@@AEAAXPEB_WH0H0H@Z`
- size: `4593`
- prototype: `void __usercall(CDBLogSTVF *__hidden this@<rcx>, const wchar_t *Source@<rdx>, int@<r8d>, const wchar_t *@<r9>, int, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x101f15040`

## callees

- `0x100401490`
- `0x100415e90`
- `0x100569c10`
- `0x1005f1f00`
- `0x10072d4d0`
- `0x10072d690`
- `0x1011ff120`
- `0x101c70730`
- `0x101c7b390`
- `0x101cfc260`
- `0x101ef2a70`
- `0x101f024b0`
- `0x101f114d0`
- `0x101f14f90`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x101f11931`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11986`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11ace`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11b23`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11d6e`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11dc5`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11ee8`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11f3d`
- `KERNEL32!QueryPerformanceCounter` at `0x101f12348`
- `KERNEL32!QueryPerformanceCounter` at `0x101f123a0`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11931`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11986`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11ace`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11b23`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11d6e`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11dc5`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11ee8`
- `KERNEL32!QueryPerformanceCounter` at `0x101f11f3d`
- `KERNEL32!QueryPerformanceCounter` at `0x101f12348`
- `KERNEL32!QueryPerformanceCounter` at `0x101f123a0`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101f117c6`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101f11c36`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101f117c6`
- `sqlTsEs!?CompareStringWEnglishNoCase@@YAHKEPEFB_WH0H@Z` at `0x101f11c36`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101f119f3`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101f11f91`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101f1240e`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101f118d4`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101f11a71`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101f11d10`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101f11e8b`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101f122ea`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101f11945`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101f11ae2`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101f11d83`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101f11efc`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101f1235d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101f11922`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101f11976`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101f11abf`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101f11b13`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101f11d5e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101f11db4`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101f11ed9`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101f11f2d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101f12338`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101f1238f`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101f11539`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101f12214`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101f115b4`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101f115b4`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x101f1162c`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x101f1162c`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101f11ff7`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101f121f5`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101f11ff7`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x101f121f5`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f11820`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f11c88`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f11820`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101f11c88`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f1156b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f115ff`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f1167e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f116e7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f11775`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f11873`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f11bf5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f11ca2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f120ef`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f1156b`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f115ff`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f1167e`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f116e7`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f11775`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f11873`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f11bf5`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f11ca2`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101f120ef`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101f12489`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101f12529`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101f125f3`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101f12489`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101f12529`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101f125f3`
- `sqldk!SystemThread_TlsIndex` at `0x101f118f4`
- `sqldk!SystemThread_TlsIndex` at `0x101f11a91`
- `sqldk!SystemThread_TlsIndex` at `0x101f11d30`
- `sqldk!SystemThread_TlsIndex` at `0x101f11eab`
- `sqldk!SystemThread_TlsIndex` at `0x101f1230a`
- `sqldk!SystemThread_TlsIndex` at `0x101f1245a`
- `sqldk!SystemThread_TlsIndex` at `0x101f124fa`
- `sqldk!SystemThread_TlsIndex` at `0x101f125c4`
- `sqldk!SystemThread_TlsOffset` at `0x101f118fd`
- `sqldk!SystemThread_TlsOffset` at `0x101f11a9a`
- `sqldk!SystemThread_TlsOffset` at `0x101f11d39`
- `sqldk!SystemThread_TlsOffset` at `0x101f11eb4`
- `sqldk!SystemThread_TlsOffset` at `0x101f12313`
- `sqldk!SystemThread_TlsOffset` at `0x101f12463`
- `sqldk!SystemThread_TlsOffset` at `0x101f12503`
- `sqldk!SystemThread_TlsOffset` at `0x101f125cd`
- `sqldk!??_V@YAXPEAX@Z` at `0x101f1269b`
- `sqldk!??_V@YAXPEAX@Z` at `0x101f1269b`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101f119ff`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101f11f9d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101f1241a`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101f119ff`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101f11f9d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101f1241a`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x101f12161`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x101f12161`

## pseudocode

```c

```

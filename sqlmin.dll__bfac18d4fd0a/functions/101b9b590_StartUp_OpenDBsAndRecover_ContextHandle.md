# StartUp::OpenDBsAndRecover(ContextHandle)

- ea: `0x101b9b590`
- end: `0x101b9dac6`
- name: `?OpenDBsAndRecover@StartUp@@SAXVContextHandle@@@Z`
- size: `9526`
- prototype: ``
- caller_count: `1`
- callee_count: `91`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x101b948c0`

## callees

- `0x100401380`
- `0x1004013f0`
- `0x100401490`
- `0x100402000`
- `0x100402200`
- `0x100403d90`
- `0x100415c30`
- `0x1004162a0`
- `0x10041e3e0`
- `0x10042b3d0`
- `0x10042d300`
- `0x10042d9c0`
- `0x100449bd0`
- `0x10047b3f0`
- `0x1004ab1b0`
- `0x1004ab250`
- `0x1004c37b0`
- `0x1004c39d0`
- `0x1004d9cf0`
- `0x1004e8470`
- `0x1005486c0`
- `0x1005a6310`
- `0x1005d8b90`
- `0x100626050`
- `0x1006c5e70`
- `0x1006c6280`
- `0x1006c6560`
- `0x1007ccfd0`
- `0x1007cd170`
- `0x100848a30`
- `0x100ac54f0`
- `0x100bceca0`
- `0x101108950`
- `0x10111cf10`
- `0x101241ac0`
- `0x1012456f0`
- `0x1016491a0`
- `0x10168e660`
- `0x1016dff40`
- `0x1016f3cc0`
- `0x1016f4080`
- `0x10170ebe0`
- `0x101714ec0`
- `0x1017344f0`
- `0x101877c10`
- `0x1019724c0`
- `0x101ad60e0`
- `0x101af0500`
- `0x101b939f0`
- `0x101b93c70`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x101b9c128`
- `KERNEL32!VirtualFree` at `0x101b9c128`
- `KERNEL32!VirtualProtect` at `0x101b9bf5b`
- `KERNEL32!VirtualProtect` at `0x101b9bf5b`
- `KERNEL32!GetComputerNameExW` at `0x101b9cdb6`
- `KERNEL32!GetComputerNameExW` at `0x101b9cdb6`
- `KERNEL32!QueryPerformanceCounter` at `0x101b9b95f`
- `KERNEL32!QueryPerformanceCounter` at `0x101b9ba25`
- `KERNEL32!QueryPerformanceCounter` at `0x101b9bd70`
- `KERNEL32!QueryPerformanceCounter` at `0x101b9be36`
- `KERNEL32!QueryPerformanceCounter` at `0x101b9b95f`
- `KERNEL32!QueryPerformanceCounter` at `0x101b9ba25`
- `KERNEL32!QueryPerformanceCounter` at `0x101b9bd70`
- `KERNEL32!QueryPerformanceCounter` at `0x101b9be36`
- `KERNEL32!GetLastError` at `0x101b9cde8`
- `KERNEL32!GetLastError` at `0x101b9cde8`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101b9d337`
- `sqlTsEs!?PDCServer@CDefaultCollation@@SAPEAV1@XZ` at `0x101b9d337`
- `sqlTsEs!?FGetCollationName@@YA_NKPEA_WPEAH@Z` at `0x101b9d356`
- `sqlTsEs!?FGetCollationName@@YA_NKPEA_WPEAH@Z` at `0x101b9d356`
- `sqlTsEs!?WszFromWsLen@@YAPEA_WPEAVIMemObj@@PEB_WH@Z` at `0x101b9cc9d`
- `sqlTsEs!?WszFromWsLen@@YAPEA_WPEAVIMemObj@@PEB_WH@Z` at `0x101b9cc9d`
- `sqldk!?IsWindows@OsInfo@@QEBA?B_NXZ` at `0x101b9d7c2`
- `sqldk!?IsWindows@OsInfo@@QEBA?B_NXZ` at `0x101b9d7c2`
- `sqldk!?IsWow64@SOS_OS@@SAHXZ` at `0x101b9cbae`
- `sqldk!?IsWow64@SOS_OS@@SAHXZ` at `0x101b9ce2a`
- `sqldk!?IsWow64@SOS_OS@@SAHXZ` at `0x101b9cbae`
- `sqldk!?IsWow64@SOS_OS@@SAHXZ` at `0x101b9ce2a`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101b9c2d3`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101b9c5b7`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101b9d4fd`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101b9d618`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x101b9d640`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x101b9b6cd`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x101b9b6dd`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x101b9c8b1`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x101b9c8c0`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x101b9c8cf`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x101b9c8de`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x101b9c8ed`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x101b9cb87`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x101b9cc93`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101b9c06b`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101b9c0bc`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101b9b8b6`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101b9bcc7`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101b9c3dd`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101b9ccbd`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101b9d18c`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101b9d6c3`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x101b9d7b3`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x101b9c10d`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101b9b9b9`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101b9bdca`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101b9b943`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101b9ba09`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101b9bd54`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101b9be1a`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101b9d0b3`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101b9d379`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x101b9d41f`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x101b9c378`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x101b9d6d2`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x101b9d6d2`
- `sqldk!?NoThrowHandler@@YAHHHHHPEAD@Z` at `0x101b9d525`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101b9c461`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101b9c4a3`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101b9c4d8`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101b9d2a0`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101b9d847`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101b9c461`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101b9c4a3`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101b9c4d8`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101b9d2a0`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x101b9d847`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x101b9d238`
- `sqldk!?CreateExecSql@@YAPEAVIExecSql@@PEAVIMemObj@@PEAVICallerParse@@@Z` at `0x101b9d238`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x101b9b73a`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x101b9b73a`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x101b9bbdb`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x101b9bbdb`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101b9d5f0`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101b9da8d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101b9d5f0`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x101b9da8d`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101b9d1bf`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x101b9d1bf`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b9c663`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b9c6b3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b9cfb8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b9d26a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b9d8bc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b9d8f4`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b9c663`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b9c6b3`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b9cfb8`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b9d26a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b9d8bc`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b9d8f4`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101b9d60d`
- `sqldk!?ex_raise@@YAHHHHHZZ` at `0x101b9d60d`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x101b9c3ec`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x101b9cccc`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x101b9d19b`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x101b9c3ec`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x101b9cccc`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x101b9d19b`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101b9c9d4`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101b9cf4a`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101b9c9d4`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x101b9cf4a`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101b9b661`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101b9b765`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101b9c25d`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101b9c372`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101b9ca52`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101b9cb0a`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101b9b661`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101b9b765`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101b9c25d`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101b9c372`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101b9ca52`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x101b9cb0a`
- `sqldk!SystemThread_TlsIndex` at `0x101b9b8e6`
- `sqldk!SystemThread_TlsIndex` at `0x101b9bb34`
- `sqldk!SystemThread_TlsIndex` at `0x101b9bcf7`
- `sqldk!SystemThread_TlsIndex` at `0x101b9c20c`
- `sqldk!SystemThread_TlsIndex` at `0x101b9c413`
- `sqldk!SystemThread_TlsIndex` at `0x101b9c7b7`
- `sqldk!SystemThread_TlsIndex` at `0x101b9c852`
- `sqldk!SystemThread_TlsIndex` at `0x101b9c99d`
- `sqldk!SystemThread_TlsIndex` at `0x101b9cf0a`
- `sqldk!SystemThread_TlsIndex` at `0x101b9d038`
- `sqldk!SystemThread_TlsIndex` at `0x101b9d200`
- `sqldk!SystemThread_TlsIndex` at `0x101b9d5b0`
- `sqldk!SystemThread_TlsIndex` at `0x101b9d9c2`
- `sqldk!SystemThread_TlsIndex` at `0x101b9d9f7`
- `sqldk!SystemThread_TlsIndex` at `0x101b9da55`
- `sqldk!SystemThread_TlsOffset` at `0x101b9b8ef`
- `sqldk!SystemThread_TlsOffset` at `0x101b9bb3d`
- `sqldk!SystemThread_TlsOffset` at `0x101b9bd00`
- `sqldk!SystemThread_TlsOffset` at `0x101b9c215`
- `sqldk!SystemThread_TlsOffset` at `0x101b9c41c`
- `sqldk!SystemThread_TlsOffset` at `0x101b9c7c0`
- `sqldk!SystemThread_TlsOffset` at `0x101b9c85b`
- `sqldk!SystemThread_TlsOffset` at `0x101b9c9a6`
- `sqldk!SystemThread_TlsOffset` at `0x101b9cf13`
- `sqldk!SystemThread_TlsOffset` at `0x101b9d041`
- `sqldk!SystemThread_TlsOffset` at `0x101b9d209`
- `sqldk!SystemThread_TlsOffset` at `0x101b9d5b9`
- `sqldk!SystemThread_TlsOffset` at `0x101b9d9cb`
- `sqldk!SystemThread_TlsOffset` at `0x101b9da00`
- `sqldk!SystemThread_TlsOffset` at `0x101b9da5e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101b9d222`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101b9d5d2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101b9da77`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101b9d222`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101b9d5d2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101b9da77`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101b9c07d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101b9c0ce`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101b9c07d`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101b9c0ce`
- `sqllang!?CreateSystemTimerTask@@YA?AW4SOS_RESULT@@PEB_WP6A?AW4SOS_TIMERRESULT@@PEAXPEAK2@Z1KP6AX1@Z@Z` at `0x101b9c3a6`
- `sqllang!?CreateSystemTimerTask@@YA?AW4SOS_RESULT@@PEB_WP6A?AW4SOS_TIMERRESULT@@PEAXPEAK2@Z1KP6AX1@Z@Z` at `0x101b9c3a6`
- `sqllang!?OfficeLockdown@@YAXGPEB_WH@Z` at `0x101b9d680`
- `sqllang!?OfficeLockdown@@YAXGPEB_WH@Z` at `0x101b9d680`
- `sqllang!?FConfigSysDbForUserInstance@@YAHXZ` at `0x101b9c454`
- `sqllang!?FConfigSysDbForUserInstance@@YAHXZ` at `0x101b9c454`
- `sqllang!?VerifyTrust@@YAXXZ` at `0x101b9c4f0`
- `sqllang!?VerifyTrust@@YAXXZ` at `0x101b9c4f0`
- `sqllang!?InitHttp@@YAXPEB_WG@Z` at `0x101b9c524`
- `sqllang!?InitHttp@@YAXPEB_WG@Z` at `0x101b9c524`
- `sqllang!?GetTdsHandle@@YAPEAUtds_handle@@XZ` at `0x101b9b62c`
- `sqllang!?GetTdsHandle@@YAPEAUtds_handle@@XZ` at `0x101b9b62c`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101b9c3ce`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101b9ce08`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101b9cffd`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101b9d4cf`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101b9d6dc`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101b9d6f6`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101b9d98f`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101b9c3ce`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101b9ce08`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101b9cffd`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101b9d4cf`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101b9d6dc`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101b9d6f6`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x101b9d98f`
- `sqlfabric!HadrFabricXEInitCall` at `0x101b9c4de`
- `sqlfabric!HadrFabricXEInitCall` at `0x101b9c4de`
- `rbio!RbIoInitializeXEEngine` at `0x101b9c483`
- `rbio!RbIoInitializeXEEngine` at `0x101b9c483`
- `fidotransport!FidoTransportInitializeXEEngine` at `0x101b9c4b8`
- `fidotransport!FidoTransportInitializeXEEngine` at `0x101b9c4b8`
- `sbs!?RegisterSbsDetourFunction@@YAXXZ` at `0x101b9d90d`
- `sbs!?RegisterSbsDetourFunction@@YAXXZ` at `0x101b9d90d`
- `sbs!?PrepareBeforeSignalSbs@@YAXXZ` at `0x101b9d930`
- `sbs!?PrepareBeforeSignalSbs@@YAXXZ` at `0x101b9d930`
- `sbs!?SignalSbsDetourDll@@YAXXZ` at `0x101b9d936`

## string_xrefs

- `0x101b9d913`: `FileServiceReady`
- `0x101b9d93c`: `FileServiceReady`
- `0x101b9cb56`: `OpenDBsAndRecover`
- `0x101b9c48d`: `StartUp::OpenDBsAndRecover`
- `0x101b9c4c2`: `StartUp::OpenDBsAndRecover`
- `0x101b9b645`: `OpenDBsAndRecover(), SetSecuritySA`
- `0x101b9d1d0`: `DECLARE @UserDatabaseCount INT = (SELECT COUNT (*) FROM master.sys.databases WHERE name NOT IN ('master', 'model', 'msdb', 'tempdb')) IF (@UserDatabaseCount > 0) BEGIN 	RAISERROR(%ld, -1, -1) WITH LOG END `
- `0x101b9b744`: `start model tempdb`
- `0x101b9d8fa`: `Orca: Register SBS IO functions and their addresses in the registry.`
- `0x101b9cdfa`: `GetComputerNameEx() initialization failed. Aborting Initilialization`
- `0x101b9cea0`: `the SQL Server instance is not running as a service`

## pseudocode

```c
// Hidden C++ exception states: #wind=26 #try_helpers=1
void __fastcall StartUp::OpenDBsAndRecover(__int64 a1)
{
  char v2; // al
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rsi
  bool v6; // zf
  __int64 v7; // rsi
  __int64 v8; // rsi
  DirtyPageMgr *QuadPart; // rax
  DirtyPageMgr *v10; // rax
  signed __int64 v11; // rax
  _QWORD *v12; // rdx
  _QWORD *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rax
  _QWORD *v18; // rsi
  ISOSHost_TaskImpl *v19; // rcx
  SOS_Node *v20; // rcx
  __int64 v21; // r14
  ISOSHost_TaskImpl *v22; // rsi
  _QWORD *v23; // r15
  __int64 v24; // rsi
  __int64 v25; // rsi
  __int64 v26; // rsi
  DirtyPageMgr *v27; // rax
  DirtyPageMgr *v28; // rax
  signed __int64 v29; // rax
  _QWORD *v30; // rsi
  void *v31; // r14
  _QWORD *v32; // rcx
  _QWORD *v33; // rcx
  unsigned __int64 v34; // rax
  SOS_ObjectStore *v35; // rcx
  unsigned int PoolIdForObject; // eax
  char v37; // r9
  _QWORD *v38; // r8
  __int64 v39; // r10
  _QWORD *v40; // rcx
  __int64 v41; // rcx
  int v42; // r8d
  int v43; // r8d
  _QWORD *v44; // rcx
  unsigned int MasterDbId; // ecx
  DBTABLE *v46; // r8
  struct DBTABLE *v47; // rsi
  _BYTE *v48; // r13
  bool v49; // r12
  int v50; // eax
  __int64 v51; // rdx
  _BOOL8 v52; // rcx
  char v53; // al
  __int64 v54; // rax
  _QWORD *v55; // r8
  __int64 v56; // rax
  struct CSessionTraceFlags **v57; // rax
  struct CSessionTraceFlags *v58; // rcx
  unsigned int v59; // ecx
  unsigned __int16 v60; // ax
  __int64 v61; // rcx
  DWORD v62; // eax
  __int64 v63; // rax
  __int64 v64; // rdi
  __int64 v65; // rdx
  __int64 v66; // rcx
  signed int LastError; // eax
  __int64 v68; // rdx
  const struct _GUID *v69; // r9
  struct CSessionTraceFlags *v70; // rcx
  __int64 v71; // rax
  struct CSessionTraceFlags **v72; // rax
  __int64 v73; // rax
  int v74; // eax
  struct __crt_locale_pointers *DefaultLocale; // rax
  int v76; // eax
  __int64 v77; // rdi
  __int64 v78; // rcx
  struct IExecSql *ExecSql; // rdi
  __int64 v80; // rdx
  __int64 v81; // rcx
  unsigned int v82; // edi
  __int64 v83; // rdi
  struct Worker *v84; // rcx
  int v85; // edi
  unsigned __int16 v86; // ax
  __int64 v87; // rdx
  __int64 v88; // rcx
  char v89; // al
  struct CFidoGLMManager *CFidoGLMManager; // rax
  __int64 v92; // rdx
  __int64 v93; // rcx
  _BOOL8 v94; // rdi
  unsigned int v95; // edi
  __int64 v96; // rbx
  struct Worker *v97; // rcx
  const struct SQLError *CurrentException; // rax
  int v99; // [rsp+20h] [rbp-1B48h]
  int (*v100)(int, int, int, int, char *); // [rsp+20h] [rbp-1B48h]
  __int64 v101; // [rsp+30h] [rbp-1B38h]
  __int64 v102; // [rsp+30h] [rbp-1B38h]
  char v103; // [rsp+40h] [rbp-1B28h]
  bool v104; // [rsp+41h] [rbp-1B27h]
  char v105; // [rsp+42h] [rbp-1B26h]
  DBTABLE *v106; // [rsp+48h] [rbp-1B20h]
  int v107; // [rsp+54h] [rbp-1B14h] BYREF
  char v108; // [rsp+58h] [rbp-1B10h]
  char v109; // [rsp+59h] [rbp-1B0Fh]
  bool v110; // [rsp+5Ah] [rbp-1B0Eh]
  bool v111; // [rsp+5Bh] [rbp-1B0Dh]
  char v112; // [rsp+5Ch] [rbp-1B0Ch]
  char v113; // [rsp+5Dh] [rbp-1B0Bh]
  char v114; // [rsp+5Eh] [rbp-1B0Ah]
  char v115; // [rsp+5Fh] [rbp-1B09h]
  char v116; // [rsp+60h] [rbp-1B08h]
  char v117; // [rsp+61h] [rbp-1B07h]
  char v118; // [rsp+62h] [rbp-1B06h]
  char v119; // [rsp+63h] [rbp-1B05h]
  char v120; // [rsp+64h] [rbp-1B04h]
  bool v121; // [rsp+65h] [rbp-1B03h]
  char v122; // [rsp+66h] [rbp-1B02h]
  char v123; // [rsp+67h] [rbp-1B01h]
  char v124; // [rsp+68h] [rbp-1B00h]
  char v125; // [rsp+69h] [rbp-1AFFh]
  char v126; // [rsp+6Ah] [rbp-1AFEh]
  char v127; // [rsp+6Bh] [rbp-1AFDh]
  char v128; // [rsp+6Ch] [rbp-1AFCh]
  char v129; // [rsp+6Dh] [rbp-1AFBh]
  int v130; // [rsp+70h] [rbp-1AF8h]
  char v131; // [rsp+74h] [rbp-1AF4h]
  unsigned int v132; // [rsp+78h] [rbp-1AF0h] BYREF
  int v133; // [rsp+7Ch] [rbp-1AECh]
  _QWORD *v134; // [rsp+80h] [rbp-1AE8h]
  void **v135; // [rsp+88h] [rbp-1AE0h] BYREF
  struct IMetadataAccess *v136; // [rsp+90h] [rbp-1AD8h]
  __int64 v137; // [rsp+98h] [rbp-1AD0h] BYREF
  signed __int64 v138; // [rsp+A0h] [rbp-1AC8h]
  volatile signed __int64 *v139; // [rsp+A8h] [rbp-1AC0h]
  DBTABLE *v140; // [rsp+B0h] [rbp-1AB8h]
  unsigned int v141; // [rsp+B8h] [rbp-1AB0h]
  DWORD nSize; // [rsp+C0h] [rbp-1AA8h] BYREF
  unsigned int v143; // [rsp+C4h] [rbp-1AA4h] BYREF
  int v144; // [rsp+C8h] [rbp-1AA0h] BYREF
  int started; // [rsp+CCh] [rbp-1A9Ch]
  int v146; // [rsp+D0h] [rbp-1A98h] BYREF
  __int64 v147; // [rsp+D8h] [rbp-1A90h]
  DirtyPageMgr *v148; // [rsp+E0h] [rbp-1A88h] BYREF
  DirtyPageMgr *v149; // [rsp+E8h] [rbp-1A80h] BYREF
  LPVOID lpAddress; // [rsp+F0h] [rbp-1A78h]
  BOOL v151; // [rsp+F8h] [rbp-1A70h]
  BOOL v152; // [rsp+FCh] [rbp-1A6Ch]
  int v153; // [rsp+100h] [rbp-1A68h] BYREF
  int v154; // [rsp+104h] [rbp-1A64h] BYREF
  int v155; // [rsp+108h] [rbp-1A60h] BYREF
  int v156; // [rsp+10Ch] [rbp-1A5Ch] BYREF
  signed __int64 UniqueThread_low; // [rsp+110h] [rbp-1A58h]
  __int64 v158; // [rsp+118h] [rbp-1A50h]
  DirtyPageMgr *v159; // [rsp+120h] [rbp-1A48h] BYREF
  DirtyPageMgr *v160; // [rsp+128h] [rbp-1A40h] BYREF
  signed __int64 v161; // [rsp+130h] [rbp-1A38h]
  char *v162; // [rsp+138h] [rbp-1A30h]
  volatile signed __int64 *v163; // [rsp+140h] [rbp-1A28h] BYREF
  int v164; // [rsp+148h] [rbp-1A20h]
  DirtyPageMgr *v165; // [rsp+150h] [rbp-1A18h] BYREF
  _QWORD *v166; // [rsp+158h] [rbp-1A10h]
  __int64 v167; // [rsp+160h] [rbp-1A08h] BYREF
  DirtyPageMgr *v168; // [rsp+168h] [rbp-1A00h] BYREF
  _DWORD v169[18]; // [rsp+170h] [rbp-19F8h] BYREF
  DWORD flOldProtect[19]; // [rsp+1B8h] [rbp-19B0h] BYREF
  int v171; // [rsp+204h] [rbp-1964h]
  unsigned int v172; // [rsp+208h] [rbp-1960h]
  int v173; // [rsp+20Ch] [rbp-195Ch]
  unsigned int v174; // [rsp+210h] [rbp-1958h]
  int v175; // [rsp+218h] [rbp-1950h]
  int v176; // [rsp+220h] [rbp-1948h]
  __int64 v177; // [rsp+228h] [rbp-1940h]
  LARGE_INTEGER PerformanceCount; // [rsp+230h] [rbp-1938h] BYREF
  DirtyPageMgr *v179; // [rsp+238h] [rbp-1930h]
  LARGE_INTEGER v180; // [rsp+240h] [rbp-1928h] BYREF
  DirtyPageMgr *v181; // [rsp+248h] [rbp-1920h]
  __int64 v182; // [rsp+250h] [rbp-1918h]
  LARGE_INTEGER v183; // [rsp+258h] [rbp-1910h] BYREF
  DirtyPageMgr *v184; // [rsp+260h] [rbp-1908h]
  LARGE_INTEGER v185; // [rsp+268h] [rbp-1900h] BYREF
  DirtyPageMgr *v186; // [rsp+270h] [rbp-18F8h]
  signed __int32 v187; // [rsp+278h] [rbp-18F0h]
  signed __int32 v188; // [rsp+27Ch] [rbp-18ECh]
  __int64 v189; // [rsp+280h] [rbp-18E8h]
  unsigned __int64 v190; // [rsp+288h] [rbp-18E0h]
  __int64 v191; // [rsp+290h] [rbp-18D8h]
  struct CSessionTraceFlags *v192; // [rsp+298h] [rbp-18D0h]
  DBMgr *v193; // [rsp+2A0h] [rbp-18C8h]
  __int64 v194; // [rsp+2A8h] [rbp-18C0h]
  struct CSessionTraceFlags *v195; // [rsp+2B0h] [rbp-18B8h]
  const wchar_t *v196; // [rsp+2B8h] [rbp-18B0h]
  const wchar_t *v197; // [rsp+2C0h] [rbp-18A8h]
  wchar_t *v198; // [rsp+2C8h] [rbp-18A0h]
  __int64 v199; // [rsp+2D0h] [rbp-1898h]
  int v200; // [rsp+2D8h] [rbp-1890h]
  int v201; // [rsp+2DCh] [rbp-188Ch]
  int v202; // [rsp+2E0h] [rbp-1888h]
  int v203; // [rsp+2E8h] [rbp-1880h] BYREF
  __int64 v204; // [rsp+2F0h] [rbp-1878h]
  _BYTE v205[16]; // [rsp+2F8h] [rbp-1870h] BYREF
  _QWORD *ThreadLocalStoragePointer; // [rsp+308h] [rbp-1860h]
  __int64 v207; // [rsp+310h] [rbp-1858h]
  __int64 v208; // [rsp+318h] [rbp-1850h]
  DirtyPageMgr **v209; // [rsp+320h] [rbp-1848h]
  DirtyPageMgr *v210; // [rsp+328h] [rbp-1840h]
  DirtyPageMgr **v211; // [rsp+330h] [rbp-1838h]
  DirtyPageMgr **v212; // [rsp+338h] [rbp-1830h]
  DirtyPageMgr **v213; // [rsp+340h] [rbp-1828h]
  signed __int64 v214; // [rsp+348h] [rbp-1820h]
  __int64 v215; // [rsp+350h] [rbp-1818h]
  _QWORD *v216; // [rsp+358h] [rbp-1810h]
  __int64 v217; // [rsp+360h] [rbp-1808h]
  _QWORD *v218; // [rsp+368h] [rbp-1800h]
  __int64 v219; // [rsp+370h] [rbp-17F8h]
  __int64 v220; // [rsp+378h] [rbp-17F0h]
  __int64 v221; // [rsp+380h] [rbp-17E8h]
  __int64 v222; // [rsp+388h] [rbp-17E0h]
  _QWORD *v223; // [rsp+390h] [rbp-17D8h]
  signed __int64 v224; // [rsp+398h] [rbp-17D0h]
  signed __int64 v225; // [rsp+3A0h] [rbp-17C8h]
  _QWORD *v226; // [rsp+3A8h] [rbp-17C0h]
  __int64 v227; // [rsp+3B0h] [rbp-17B8h]
  __int64 v228; // [rsp+3B8h] [rbp-17B0h]
  DirtyPageMgr **v229; // [rsp+3C0h] [rbp-17A8h]
  DirtyPageMgr *v230; // [rsp+3C8h] [rbp-17A0h]
  DirtyPageMgr **v231; // [rsp+3D0h] [rbp-1798h]
  DirtyPageMgr **v232; // [rsp+3D8h] [rbp-1790h]
  DirtyPageMgr **v233; // [rsp+3E0h] [rbp-1788h]
  __int64 v234; // [rsp+3E8h] [rbp-1780h]
  __int64 v235; // [rsp+3F0h] [rbp-1778h]
  _QWORD *v236; // [rsp+3F8h] [rbp-1770h]
  _QWORD *v237; // [rsp+400h] [rbp-1768h]
  _QWORD *v238; // [rsp+408h] [rbp-1760h]
  _QWORD *v239; // [rsp+410h] [rbp-1758h]
  __int64 v240; // [rsp+418h] [rbp-1750h]
  __int64 v241; // [rsp+420h] [rbp-1748h]
  _QWORD *v242; // [rsp+428h] [rbp-1740h]
  _QWORD *v243; // [rsp+430h] [rbp-1738h]
  _QWORD *v244; // [rsp+438h] [rbp-1730h]
  _QWORD *v245; // [rsp+440h] [rbp-1728h]
  __int64 v246; // [rsp+448h] [rbp-1720h]
  const wchar_t *v247; // [rsp+450h] [rbp-1718h]
  const wchar_t *v248; // [rsp+458h] [rbp-1710h]
  const wchar_t *v249; // [rsp+460h] [rbp-1708h]
  wchar_t *v250; // [rsp+468h] [rbp-1700h]
  const wchar_t *v251; // [rsp+470h] [rbp-16F8h]
  __int64 v252; // [rsp+478h] [rbp-16F0h]
  wchar_t *v253; // [rsp+480h] [rbp-16E8h]
  wchar_t *v254; // [rsp+488h] [rbp-16E0h]
  __int64 *v255; // [rsp+490h] [rbp-16D8h]
  __int64 *v256; // [rsp+498h] [rbp-16D0h]
  __int64 v257; // [rsp+4A0h] [rbp-16C8h]
  struct IMetadataAccess *v258; // [rsp+4A8h] [rbp-16C0h]
  __int64 *v259; // [rsp+4B0h] [rbp-16B8h]
  __int64 *v260; // [rsp+4B8h] [rbp-16B0h]
  __int64 v261; // [rsp+4C0h] [rbp-16A8h]
  __int64 v262; // [rsp+4C8h] [rbp-16A0h]
  wchar_t *v263; // [rsp+4D0h] [rbp-1698h]
  __int64 v264; // [rsp+4D8h] [rbp-1690h]
  struct IExecSql *v265; // [rsp+4E0h] [rbp-1688h]
  struct IExecSql *v266; // [rsp+4E8h] [rbp-1680h]
  __int64 v267; // [rsp+4F0h] [rbp-1678h]
  wchar_t *v268; // [rsp+4F8h] [rbp-1670h]
  __int64 v269; // [rsp+500h] [rbp-1668h]
  const wchar_t *v270; // [rsp+508h] [rbp-1660h]
  const wchar_t *v271; // [rsp+510h] [rbp-1658h]
  __int64 v272; // [rsp+518h] [rbp-1650h]
  __int64 v273; // [rsp+520h] [rbp-1648h]
  struct Worker *v274; // [rsp+528h] [rbp-1640h]
  __int64 v275; // [rsp+530h] [rbp-1638h]
  __int64 v276; // [rsp+538h] [rbp-1630h]
  __int64 v277; // [rsp+540h] [rbp-1628h]
  signed __int64 v278; // [rsp+548h] [rbp-1620h]
  signed __int64 v279; // [rsp+550h] [rbp-1618h]
  __int64 v280; // [rsp+568h] [rbp-1600h]
  __int64 v281; // [rsp+570h] [rbp-15F8h]
  _BYTE v282[64]; // [rsp+578h] [rbp-15F0h] BYREF
  _BYTE v283[24]; // [rsp+5B8h] [rbp-15B0h] BYREF
  _BYTE v284[40]; // [rsp+5D0h] [rbp-1598h] BYREF
  WCHAR Buffer[20]; // [rsp+5F8h] [rbp-1570h] BYREF
  wchar_t v286[128]; // [rsp+620h] [rbp-1548h] BYREF
  wchar_t v287[264]; // [rsp+720h] [rbp-1448h] BYREF
  wchar_t v288[264]; // [rsp+930h] [rbp-1238h] BYREF
  wchar_t v289[2048]; // [rsp+B40h] [rbp-1028h] BYREF

  v252 = -2;
  v167 = 0;
  v2 = dword_10317A9FC;
  if ( (dword_10317A9FC & 1) != 0 )
  {
    dword_10316ECB0 |= 1u;
    scierrlog(0x44F8u);
    scierrlog(0x44FAu);
    v2 = dword_10317A9FC;
  }
  if ( (v2 & 4) != 0 )
  {
    dword_10316ECB0 |= 0x1000u;
    *((_BYTE *)GetTdsHandle() + 528) = 1;
  }
  if ( !(unsigned int)qword_1033C1298(0) )
  {
    scierrlog(0x42E0u, L"OpenDBsAndRecover(), SetSecuritySA");
    SQLExit(4, 0, 1066);
  }
  if ( byte_10317AD42 >= 0 )
  {
    if ( (byte_10317AD43 & 1) != 0 )
    {
      scierrlog(0xD4Bu);
    }
    else if ( (byte_10317AD43 & 2) != 0 )
    {
      scierrlog(0x44FDu);
    }
  }
  else
  {
    scierrlog(0x44FCu);
  }
  ExcHandler::ExcHandler((ExcHandler *)v282, 0, 0, 0, (int (*)(int, int, int, int, char *))HandleAndNoteToErrorlog, 0);
  qword_1033C1290(g_pmoGlobal, &qword_1031720C8, &qword_1031720D0);
  qword_1031720D8 = qword_1033C12B0(g_pmoGlobal);
  v129 = (unsigned __int8)byte_10317AD42 >> 7;
  if ( byte_10317AD42 < 0 || (v131 = byte_10317AD43, (byte_10317AD43 & 1) != 0) )
  {
    DBMgr::SetTempDbReady(qword_10316ECA0);
    EventManualInternal<SuspendQueueSLock>::Signal(&StartUp::sm_ResourceModelAndTempdbLocked, 0);
    goto LABEL_114;
  }
  if ( (unsigned int)SOS_OS::EnqueueTask(StartUp::StartModelAndTempdb, 0, 0, &v167, -1) )
  {
    scierrlog(0x42E0u, L"start model tempdb");
    SQLExit(5, 17120, 1066);
    goto LABEL_114;
  }
  v3 = v167 + 16;
  v177 = v167 + 16;
  v187 = _InterlockedDecrement((volatile signed __int32 *)(v167 + 40));
  v188 = v187;
  if ( v187 )
    goto LABEL_114;
  if ( *(_QWORD *)(v177 + 8) )
  {
    TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v177);
    goto LABEL_114;
  }
  v4 = v3 - 16;
  if ( !v3 )
    v4 = 0;
  v134 = (_QWORD *)v4;
  v262 = v4 + 184;
  if ( *(_DWORD *)(v4 + 184) == 2 )
  {
    v267 = v134[20];
    v163 = (volatile signed __int64 *)(v267 + 4952);
    v164 = 0;
    v276 = v267 + 4952;
    v277 = 0;
    v280 = 0;
    v160 = 0;
    v158 = 0;
    UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    v200 = 256;
    v281 = v267 + 4952;
    if ( *(_DWORD *)(v267 + 4952) )
    {
      v151 = 0;
    }
    else
    {
      v278 = _InterlockedCompareExchange64(v163, UniqueThread_low, 0);
      v279 = v278;
      v151 = v278 == 0;
      if ( !v278 )
      {
LABEL_48:
        v164 = 1;
        v12 = v134;
        v13 = (_QWORD *)v134[1];
        v216 = v13;
        v14 = *v134;
        v217 = v14;
        *(_QWORD *)(v14 + 8) = v13;
        *v13 = v14;
        v12[1] = 0;
        *v12 = 0;
        SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(&v163);
        goto LABEL_49;
      }
    }
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84
      && (v201 = 88,
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer,
          v5 = ThreadLocalStoragePointer[SystemThread_TlsIndex],
          v6 = SystemThread_TlsOffset + v5 == 0,
          v7 = SystemThread_TlsOffset + v5,
          v207 = v7,
          !v6)
      && *(_QWORD *)(v7 + 272) == v7 )
    {
      v8 = *(_QWORD *)(v7 + 256);
      v208 = v8;
    }
    else
    {
      v8 = 0;
    }
    v158 = v8;
    if ( v8 )
    {
      v209 = &v168;
      v202 = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v169[6] = QueryPerformanceCounter(&PerformanceCount);
        QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
        v168 = (DirtyPageMgr *)PerformanceCount.QuadPart;
      }
      else
      {
        QuadPart = MEMORY[0x7FFE0008];
        v179 = MEMORY[0x7FFE0008];
        v168 = MEMORY[0x7FFE0008];
        v8 = v158;
      }
      v210 = QuadPart;
      v160 = QuadPart;
    }
    v169[7] = 2;
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v163, UniqueThread_low);
    else
      Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v163, v8, UniqueThread_low);
    if ( v8 )
    {
      v211 = &v159;
      v169[8] = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v169[9] = QueryPerformanceCounter(&v180);
        v10 = (DirtyPageMgr *)v180.QuadPart;
        v159 = (DirtyPageMgr *)v180.QuadPart;
      }
      else
      {
        v10 = MEMORY[0x7FFE0008];
        v181 = MEMORY[0x7FFE0008];
        v159 = MEMORY[0x7FFE0008];
        v8 = v158;
      }
      v212 = &v160;
      v213 = &v159;
      if ( v10 < v160 )
      {
        v11 = 0;
        v138 = 0;
      }
      else
      {
        v11 = v10 - v160;
        v138 = v11;
      }
      v166 = (_QWORD *)v11;
      v214 = v11;
      v215 = v8 + 3192;
      *(_QWORD *)(v8 + 3192) += v11;
    }
    goto LABEL_48;
  }
LABEL_49:
  v138 = 0;
  v169[10] = 88;
  v218 = NtCurrentTeb()->ThreadLocalStoragePointer;
  v15 = v218[SystemThread_TlsIndex];
  v6 = SystemThread_TlsOffset + v15 == 0;
  v16 = SystemThread_TlsOffset + v15;
  v219 = v16;
  if ( v6 || *(_QWORD *)(v16 + 272) != v16 )
  {
    v182 = v138;
    v18 = v134;
  }
  else
  {
    v17 = *(_QWORD *)(v16 + 256);
    v138 = v17;
    v182 = v17;
    v18 = v134;
    if ( v17 && *(_QWORD **)(v17 + 528) == v134 )
    {
      v19 = (ISOSHost_TaskImpl *)(v134 - 1);
      if ( !v134 )
        v19 = 0;
      ISOSHost_TaskImpl::`scalar deleting destructor'(v19, 0);
      goto LABEL_114;
    }
  }
  v20 = (SOS_Node *)v18[21];
  if ( v20 && *((_QWORD *)v20 + 30) && !SOS_Node::IsTaskStoreDisabled(v20) )
  {
    v220 = *(_QWORD *)(v18[21] + 240LL);
    v21 = v220;
    v22 = (ISOSHost_TaskImpl *)(v18 - 1);
    ISOSHost_TaskImpl::`scalar deleting destructor'(v22, 0);
    lpAddress = v22;
    v166 = *(_QWORD **)(v21 + 2016);
    v23 = v166 + 5;
    v139 = v166 + 5;
    v221 = 0;
    v222 = 0;
    v149 = 0;
    v147 = 0;
    v161 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    v169[11] = 256;
    v223 = v166 + 5;
    if ( *((_DWORD *)v166 + 10) )
    {
      v152 = 0;
    }
    else
    {
      v224 = _InterlockedCompareExchange64(v139, v161, 0);
      v225 = v224;
      v152 = v224 == 0;
      if ( !v224 )
      {
LABEL_85:
        v30 = v166;
        if ( v166[1] >= *v166 )
        {
          v244 = v23;
          v109 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
          if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v43 = rand();
            if ( v43 == 5 * (v43 / 5) )
              Spinlock<34,1,268435714>::UpdateStatSnapshot();
          }
          v245 = v23;
          *v23 = 0;
          ((void (__fastcall *)(LPVOID))v30[6])(lpAddress);
        }
        else
        {
          v31 = lpAddress;
          if ( *(_BYTE *)(v166[4] + 5820LL) )
          {
            v235 = v166[147] & 0x3FLL;
            v32 = &v166[2 * v235 + 18];
            v236 = v32;
            *(_QWORD *)lpAddress = *v32;
            if ( !*v32 )
              v32[1] = v31;
            *v32 = v31;
            ++v30[147];
            VirtualProtect(v31, 0x1000u, 1u, flOldProtect);
          }
          else
          {
            v33 = v166 + 16;
            v237 = v166 + 16;
            *(_QWORD *)lpAddress = v166[16];
            if ( !v30[16] )
              v30[17] = v31;
            *v33 = v31;
          }
          v34 = v30[146] + 1LL;
          v190 = v34;
          ++v30[1];
          v35 = (SOS_ObjectStore *)v30[4];
          if ( !*((_BYTE *)v35 + 5820) && v34 >= 0x20 )
          {
            PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v35, (struct SList *)v31);
            v37 = PoolIdForObject;
            flOldProtect[1] = PoolIdForObject;
            v238 = v30 + 16;
            v38 = &v30[PoolIdForObject + 148];
            v239 = v38;
            v39 = v30[16];
            v240 = v39;
            v40 = (_QWORD *)v30[17];
            if ( v40 == v30 + 16 )
            {
              v189 = 0;
            }
            else
            {
              v189 = v30[17];
              if ( v40 )
              {
                *v40 = *v38;
                *v38 = v39;
              }
            }
            v30[16] = 0;
            v30[17] = v30 + 16;
            v34 = 0;
            v190 = 0;
            v241 = 1LL << v37;
            v41 = v30[212];
            if ( (v41 & (1LL << v37)) == 0 )
              v30[212] = (1LL << v37) | v41;
          }
          v30[146] = v34;
          v242 = v23;
          v108 = (char)SOS_PublicGlobals::sm_SpinlockStatSnapshot;
          if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
          {
            v42 = rand();
            if ( v42 == 5 * (v42 / 5) )
              Spinlock<34,1,268435714>::UpdateStatSnapshot();
          }
          v243 = v23;
          *v23 = 0;
        }
        goto LABEL_114;
      }
    }
    if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84
      && (v169[12] = 88,
          v226 = NtCurrentTeb()->ThreadLocalStoragePointer,
          v24 = v226[SystemThread_TlsIndex],
          v6 = SystemThread_TlsOffset + v24 == 0,
          v25 = SystemThread_TlsOffset + v24,
          v227 = v25,
          !v6)
      && *(_QWORD *)(v25 + 272) == v25 )
    {
      v26 = *(_QWORD *)(v25 + 256);
      v228 = v26;
    }
    else
    {
      v26 = 0;
    }
    v147 = v26;
    if ( v26 )
    {
      v229 = &v165;
      v169[13] = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v169[14] = QueryPerformanceCounter(&v183);
        v27 = (DirtyPageMgr *)v183.QuadPart;
        v165 = (DirtyPageMgr *)v183.QuadPart;
      }
      else
      {
        v27 = MEMORY[0x7FFE0008];
        v184 = MEMORY[0x7FFE0008];
        v165 = MEMORY[0x7FFE0008];
        v26 = v147;
      }
      v230 = v27;
      v149 = v27;
    }
    v169[15] = 2;
    if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
      Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v139, v161);
    else
      Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v139, v26, v161);
    if ( v26 )
    {
      v231 = &v148;
      v169[16] = Base_PublicGlobals::sm_invariantTscAvailable;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        v169[17] = QueryPerformanceCounter(&v185);
        v28 = (DirtyPageMgr *)v185.QuadPart;
        v148 = (DirtyPageMgr *)v185.QuadPart;
      }
      else
      {
        v28 = MEMORY[0x7FFE0008];
        v186 = MEMORY[0x7FFE0008];
        v148 = MEMORY[0x7FFE0008];
        v26 = v147;
      }
      v232 = &v149;
      v233 = &v148;
      if ( v28 < v149 )
      {
        v29 = 0;
        v162 = 0;
      }
      else
      {
        v29 = v28 - v149;
        v162 = (char *)v29;
      }
      v162 = (char *)v29;
      v234 = v26 + 3192;
      *(_QWORD *)(v26 + 3192) += v29;
    }
    goto LABEL_85;
  }
  v44 = v18 - 1;
  if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
  {
    VirtualFree(v44, 0, 0x8000u);
  }
  else if ( v18 != (_QWORD *)8 )
  {
    ISOSHost_TaskImpl::`scalar deleting destructor'((ISOSHost_TaskImpl *)v44, 1u);
  }
LABEL_114:
  if ( dword_103172528 || (flOldProtect[2] = dword_103172574) != 0 )
    log_unlocalized_systemmetadata(
      L"Server database version max is %d and current is %d.",
      957,
      (unsigned __int16)word_1033C1050);
  AutoForcePhysMaster::AutoForcePhysMaster((AutoForcePhysMaster *)&v153);
  DBMgr::StartMaster(qword_10316ECA0);
  MasterDbId = GetMasterDbId();
  switch ( MasterDbId )
  {
    case 0x7FFCu:
      v46 = (DBTABLE *)*((_QWORD *)qword_10316ECA0 + 13);
      goto LABEL_127;
    case 0x7FFDu:
      v46 = (DBTABLE *)*((_QWORD *)qword_10316ECA0 + 14);
      goto LABEL_127;
    case 0x7FFFu:
      v46 = (DBTABLE *)*((_QWORD *)qword_10316ECA0 + 11);
      goto LABEL_127;
  }
  if ( MasterDbId <= *((_DWORD *)qword_10316ECA0 + 19) && MasterDbId )
  {
    v46 = *(DBTABLE **)(*((_QWORD *)qword_10316ECA0 + 5) + 8LL * (int)(MasterDbId - 1));
LABEL_127:
    v106 = v46;
    goto LABEL_128;
  }
  v106 = 0;
  v46 = 0;
LABEL_128:
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                    + SystemThread_TlsOffset
                                    + 8LL)
                        + 96LL)
            + 1456LL) = v153;
  v47 = v106;
  if ( !v46 || !DBTABLE::IsOkToScan(v106) )
    SQLExit(6, 3417, 1066);
  if ( *((_DWORD *)v106 + 378) == 5 )
  {
    StartUp::SignalDBMSReadyForSNI();
    EventManualInternal<SuspendQueueSLock>::Signal(&StartUp::sm_MasterdbReady, 0);
    EventManualInternal<SuspendQueueSLock>::Signal(&StartUp::sm_UserDBsReady, 0);
    StartupDependencies::SetAsCompleted(10);
    StartupDependencies::SetAsCompleted(8);
    dword_10316ECB0 |= 0x200u;
    ExcHandler::~ExcHandler((ExcHandler *)v282);
    return;
  }
  v140 = v106;
  v48 = (char *)v106 + 684;
  v49 = (*((_BYTE *)v106 + 684) & 0x20) != 0 || (unsigned int)(*((_DWORD *)s_pServerConf + 3) - 1) <= 1;
  v110 = v49;
  if ( dword_103172528 || (flOldProtect[3] = dword_103172574) != 0 || (v6 = !IsStartupScriptRunEnabled(), v50 = 0, !v6) )
    v50 = 1;
  v130 = v50;
  if ( v49 || v50 )
    dword_10316ECB0 |= 0x2000u;
  else
    StartupDependencies::SetAsCompleted(10);
  if ( (unsigned int)DBMgr::IsDownlevelDbVer(*(_WORD *)(*((_QWORD *)v106 + 578) + 1662LL), *((_BYTE *)v106 + 2361)) )
    SQLExit(7, 3417, 1066);
  v52 = CommonGlobalState::m_PerfCountersEnabled;
  v111 = CommonGlobalState::m_PerfCountersEnabled;
  if ( CommonGlobalState::m_PerfCountersEnabled )
    CreateSystemTimerTask(L"Aggregate global counters", &AggregateAllProcCounters, 0, 1000, 0);
  flOldProtect[4] = dword_10317A9FC;
  if ( (dword_10317A9FC & 8) != 0
    || (flOldProtect[5] = dword_103172574) != 0
    || (CFeatureSwitchesLangSvc::GetCurrentInstance(v52, v51), dword_103172520)
    && (v246 = SOS_OS_OsInfo, !OsInfo::IsXPlatInstance(SOS_OS_OsInfo)) )
  {
    AutoForcePhysMaster::AutoForcePhysMaster((AutoForcePhysMaster *)&v154);
    StartUp::RemapFilePaths();
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1456LL) = v154;
    v47 = v106;
  }
  flOldProtect[6] = dword_103172554;
  if ( dword_103172554 && !FConfigSysDbForUserInstance() )
    SQLExit(8);
  if ( dword_103172528 )
  {
    v53 = byte_1031852E4;
    v112 = byte_1031852E4;
    if ( !byte_1031852E4 )
    {
      if ( !(unsigned __int8)RbIoInitializeXEEngine() )
      {
        scierrlog(0x42E0u, L"StartUp::OpenDBsAndRecover");
        SQLExit(9);
      }
      v53 = byte_1031852E4;
    }
    v113 = v53;
    if ( v53 && !(unsigned __int8)FidoTransportInitializeXEEngine() )
    {
      scierrlog(0x42E0u, L"StartUp::OpenDBsAndRecover");
      SQLExit(368);
    }
    HadrFabricXEInitCall();
    byte_1031837A0 = 1;
    FireStartupPhaseTelemetryEvents();
    VerifyTrust();
  }
  qword_1033C12F8();
  BPool::InitL2BPool(qword_10317B628);
  if ( IsBdcSystemAGDBOperationRedirectEnabled() && word_103334C54 )
    InitHttp(L"localhost", word_103334C54);
  if ( dword_103172528 )
    EnableBPEOnAzure(1);
  if ( byte_10316E86D || (v114 = (unsigned __int8)byte_10317ABEB >> 7, byte_10317ABEB < 0) )
    RBPEX::Startup();
  v104 = 0;
  v103 = 0;
  if ( (unsigned int)IsContainedAGEnabledInstance() || (unsigned int)IsReplicatedMasterEnabled() )
  {
    EventManualInternal<SuspendQueueSLock>::Signal(&StartUp::sm_PhysMasterdbReady, 0);
    StartUp::SignalDBMSReadyForSNI();
    if ( !dword_103172520 )
    {
      if ( (unsigned int)IsContainedAGEnabledInstance() )
      {
        v54 = *((_QWORD *)s_pServerConf + 4);
        HIDWORD(v191) = *(_DWORD *)(v54 + 280);
        LODWORD(v191) = *(_DWORD *)(v54 + 284);
        if ( v191 != 0x10000003E80006LL )
        {
          ReInitializeModelForMasterAndMSDB();
          v103 = 1;
        }
      }
    }
    AutoForcePhysMaster::AutoForcePhysMaster((AutoForcePhysMaster *)&v155);
    v247 = L"model_replicatedmaster";
    if ( (int)StringCchPrintfW(v288, 0x105u, L"%ls.mdf") < 0 )
      utassert_fail(1u, "SUCCEEDED(hr)", "\"sql\\\\ntdbms\\\\storeng\\\\dfs\\\\startup\\\\startup.cpp\"", 5106, 0);
    v248 = L"model_replicatedmaster";
    if ( (int)StringCchPrintfW(v287, 0x105u, L"%ls.ldf") < 0 )
      utassert_fail(1u, "SUCCEEDED(hr)", "\"sql\\\\ntdbms\\\\storeng\\\\dfs\\\\startup\\\\startup.cpp\"", 5112, 0);
    v249 = L"model_replicatedmaster";
    StartDatabaseModel(0x7FFAu, L"model_replicatedmaster", v288, v287);
    DisableSSBForModelReplMaster();
    if ( v130 && (unsigned int)IsReplicatedMasterEnabled() )
    {
      StartUp::RunConfigScripts(v47, 0, 0);
      v130 = 0;
    }
    v250 = &word_103185B6E;
    if ( word_103185B6E || (unsigned int)IsContainedAGEnabledInstance() )
    {
      if ( (unsigned int)IsContainedAGEnabledInstance() )
      {
        v196 = L"model_msdb";
        StartDatabaseModel(0x7FF9u, L"model_msdb", L"model_msdbdata.mdf", L"model_msdblog.ldf");
      }
    }
    else
    {
      v104 = StartUp::DropMsDb(0);
      v251 = L"model_msdb";
      StartDatabaseModel(0x7FF9u, L"model_msdb", L"model_msdbdata.mdf", L"model_msdblog.ldf");
      if ( !dword_1031852C8 || (flOldProtect[7] = dword_10317A9FC, (dword_10317A9FC & 4) == 0) )
        SetModelMsdbToReadOnly();
    }
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1456LL) = v155;
    v47 = v106;
  }
  if ( dword_1031852C8 )
  {
    flOldProtect[8] = dword_10317A9FC;
    if ( (dword_10317A9FC & 4) != 0 )
    {
      StartUp::WaitForTempDbReady(a1);
      AutoForcePhysMaster::AutoForcePhysMaster((AutoForcePhysMaster *)&v156);
      v196 = 0;
      RecollateServer(cidNew, 0);
      v253 = &word_103185B6E;
      if ( !word_103185B6E )
        SetModelMsdbToReadOnly();
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                        + SystemThread_TlsOffset
                                        + 8LL)
                            + 96LL)
                + 1456LL) = v156;
      v47 = v106;
    }
  }
  v105 = 0;
  if ( (unsigned int)IsReplicatedMasterEnabled() || byte_10316E81B || (v115 = byte_10317AFB1, (byte_10317AFB1 & 1) != 0) )
  {
    InitializeHadrFabricManagers();
    v105 = 1;
  }
  InitPVSPageTrackerRingBuffer(g_pmoGlobal);
  InitVersionCleanupRingBuffer(g_pmoGlobal);
  InitIAMPageRangeCacheRingBuffer(g_pmoGlobal);
  InitBlobOperationsRingBuffer(g_pmoGlobal);
  InitLockDetailsRingBuffer(g_pmoGlobal);
  CTimerTask::DisableTask(&g_TimerTask, 24);
  CTimerTask::DisableTask(&g_TimerTask, 59);
  if ( !dword_103172528 )
    CTimerTask::DisableTask(&g_TimerTask, 33);
  StartGlobalTaskProc();
  v169[0] = -1;
  v169[2] = 0;
  v169[4] = 0;
  if ( (unsigned int)IsReplicatedMasterEnabled() )
  {
    if ( dword_1031852C8 || (v254 = &word_103185B6E, word_103185B6E) )
    {
      StartUp::BootReplicatedMasterFromHadr();
    }
    else
    {
      v116 = (unsigned __int8)byte_10317AFB0 >> 6;
      if ( (byte_10317AFB0 & 0x40) != 0 )
      {
LABEL_213:
        StartUp::CreateAndStartReplicatedMaster(1);
        goto LABEL_216;
      }
      v55 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v56 = *(_QWORD *)(v55[SystemThread_TlsIndex] + SystemThread_TlsOffset);
      if ( v56 )
      {
        v57 = *(struct CSessionTraceFlags ***)(v56 + 56);
        v58 = *v57;
        if ( *v57 )
        {
          v192 = *v57;
          if ( !CSessionTraceFlags::CheckSessionTraceInternal(v58, 0x2186u) )
            goto LABEL_216;
          goto LABEL_213;
        }
      }
      v192 = 0;
    }
LABEL_216:
    LOBYTE(v99) = 0;
    LOBYTE(v55) = 3;
    if ( (int)AutoDbLock::Acquire(v169, 32763, v55, 0xFFFFFFFFLL, v99, 17) < 0 )
    {
      scierrlog(17263 - (dword_103172528 != 0));
      SQLExit(10, 17263 - (unsigned int)(dword_103172528 != 0), 1066);
    }
    v59 = GetMasterDbId();
    v141 = v59;
    v193 = qword_10316ECA0;
    switch ( v59 )
    {
      case 0x7FFCu:
        v47 = (struct DBTABLE *)*((_QWORD *)qword_10316ECA0 + 13);
        break;
      case 0x7FFDu:
        v47 = (struct DBTABLE *)*((_QWORD *)qword_10316ECA0 + 14);
        break;
      case 0x7FFFu:
        v47 = (struct DBTABLE *)*((_QWORD *)qword_10316ECA0 + 11);
        break;
      default:
        if ( v59 > *((_DWORD *)qword_10316ECA0 + 19) || !v59 )
        {
          v47 = 0;
          v106 = 0;
LABEL_229:
          scierrlog(17263 - (dword_103172528 != 0));
          SQLExit(11, 17263 - (unsigned int)(dword_103172528 != 0), 1066);
          goto LABEL_230;
        }
        _mm_lfence();
        v47 = *(struct DBTABLE **)(*((_QWORD *)v193 + 5) + 8LL * (int)(v141 - 1));
        break;
    }
    v106 = v47;
    if ( v47 )
      goto LABEL_230;
    goto LABEL_229;
  }
LABEL_230:
  v135 = &AutoReadOnlyIMA::`vftable';
  v136 = 0;
  v255 = &v137;
  v256 = &v137;
  v137 = 0;
  AutoReadOnlyIMA::Init((AutoReadOnlyIMA *)&v135, L"OpenDBsAndRecover", 0x22u, 0);
  v60 = GetMasterDbId();
  if ( (unsigned int)ReconfigureSosRgFromMetadata(g_pmoGlobal, 0, v136, v60, 0, 0) )
    scierrlog(0x2A94u);
  StartUp::InitAudit();
  CFstrmNt::Init();
  if ( (unsigned int)SOS_OS::IsWow64() )
    CFilestreamFeatureState::UpdateSysconfigValueInUse(v61, 0);
  else
    CFilestreamFeatureState::Startup((CFilestreamFeatureState *)qword_103171C80);
  qword_1033C1260(v47, v136, v104);
  if ( !(unsigned int)IsReplicatedMasterEnabled() )
    StartUp::SignalDBMSReadyForSNI();
  v62 = dword_103172554;
  flOldProtect[9] = dword_103172554;
  if ( !dword_103172554 )
  {
    if ( !(unsigned int)CheckServerNameChange() )
      scierrlog(0xD4Cu);
    v62 = dword_103172554;
  }
  flOldProtect[10] = v62;
  if ( !v62 )
    CheckForRmidRemovalFromRegistry();
  flOldProtect[11] = dword_103172550;
  if ( !dword_103172550 )
  {
    flOldProtect[12] = dword_103172558;
    if ( !dword_103172558 )
    {
      v63 = (*(__int64 (__fastcall **)(struct IMetadataAccess *, _QWORD, _QWORD))(*(_QWORD *)v136 + 144LL))(v136, 0, 0);
      if ( v63 )
      {
        v64 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v63 + 8LL))(v63);
        qword_1031C91A0 = WszFromWsLen(g_pmoGlobal, *(const wchar_t **)v64, *(_DWORD *)(v64 + 8));
        dword_1031C9198 = *(unsigned __int8 *)(v64 + 8);
        if ( !dword_103172528 )
        {
          v257 = SOS_OS_OsInfo;
          if ( OsInfo::IsXPlatInstance(SOS_OS_OsInfo) )
          {
            Src = qword_1031C91A0;
            LODWORD(SourceSize) = dword_1031C9198;
          }
        }
      }
      else
      {
        dword_1031C9198 = 0;
        qword_1031C91A0 = 0;
      }
    }
  }
  v258 = v136;
  if ( v136 )
    (**(void (__fastcall ***)(struct IMetadataAccess *, __int64))v136)(v136, 1);
  v136 = 0;
  v259 = &v137;
  if ( v137 )
  {
    v194 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v137 + 72LL))(v137);
    if ( v194 )
    {
      v260 = &v137;
      if ( v137 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v137 + 32LL))(v137);
    }
  }
  else
  {
    v194 = 0;
  }
  scierrlog(0x44FFu, Src);
  flOldProtect[13] = dword_103172568;
  if ( dword_103172568 )
  {
    nSize = 16;
    if ( GetComputerNameExW(ComputerNamePhysicalNetBIOS, Buffer, &nSize) )
    {
      v261 = 30;
      Buffer[15] = 0;
      scierrlog(0x4500u, Buffer);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      CheckHrFailAndExit(LastError, "GetComputerNameEx() initialization failed. Aborting Initilialization");
    }
  }
  if ( *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v66, v65) + 1236) )
    v117 = 1;
  else
    qword_1033C1270();
  qword_1033C1268();
  if ( !(unsigned int)SOS_OS::IsWow64()
    && (dword_103334C50 || dword_10317256C)
    && dword_103334C58 != 1
    && !dword_103172528 )
  {
    if ( (dword_10316ECB0 & 1) != 0 )
    {
      scierrlog(0xA0BBu, L"the SQL Server instance is running in single-user mode");
    }
    else
    {
      flOldProtect[14] = dword_103179140;
      if ( dword_103179140 || (flOldProtect[15] = dword_103172534) != 0 || dword_103172520 )
        CHadrArManager::Startup();
      else
        scierrlog(0xA0BBu, L"the SQL Server instance is not running as a service");
    }
  }
  if ( !v105 )
    InitializeHadrFabricManagers();
  EventManualInternal<SuspendQueueSLock>::Signal(&StartUp::sm_MasterdbReady, 0);
  if ( (unsigned int)IsContainedAGEnabledInstance() && v103 )
    SetModelDbVersionInConfigure(0x10000003E80006LL);
  v118 = (unsigned __int8)byte_10317AFB0 >> 6;
  if ( (byte_10317AFB0 & 0x40) != 0 )
    goto LABEL_287;
  v70 = (struct CSessionTraceFlags *)SystemThread_TlsIndex;
  v71 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                  + SystemThread_TlsOffset);
  if ( v71 && (v72 = *(struct CSessionTraceFlags ***)(v71 + 56), (v70 = *v72) != 0) )
  {
    v195 = *v72;
    v47 = v106;
    if ( CSessionTraceFlags::CheckSessionTraceInternal(v70, 0x2186u) )
    {
LABEL_287:
      v143 = 4;
      flOldProtect[16] = dword_1031C47DC;
      v197 = L"msdb";
      if ( !StartUp::CreateAndStartAgMSDb(1, L"msdb", dword_1031C47DC, v69, &v143) )
        utassert_fail(1u, "fSucceeded", "\"sql\\\\ntdbms\\\\storeng\\\\dfs\\\\startup\\\\startup.cpp\"", 3676, 0);
      StartupDependencies::SetAsCompleted(17);
      StartUp::CreateAndStartManagedModelDb();
    }
  }
  else
  {
    v195 = 0;
    v47 = v106;
  }
  if ( v130 )
  {
    StartUp::RunConfigScripts(v47, v49, 0);
  }
  else if ( dword_1031852C8 && *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v70, v68) + 293) )
  {
    AutoForcePhysMaster::AutoForcePhysMaster((AutoForcePhysMaster *)&v144);
    StartUp::RunConfigScripts(v140, v49, 1);
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1456LL) = v144;
  }
  AutoDbLock::~AutoDbLock((AutoDbLock *)v169);
  AutoForcePhysMaster::AutoForcePhysMaster((AutoForcePhysMaster *)&v146);
  RbpexConfigureOnAzure(1);
  StartupDependencies::SetAsCompleted(19);
  dword_10316ECB0 |= 0x200u;
  v197 = 0;
  v73 = g_dbtableFactory[4](1);
  v119 = (unsigned __int8)byte_10317AD42 >> 7;
  if ( byte_10317AD42 >= 0 )
  {
    v120 = byte_10317AD43;
    if ( (byte_10317AD43 & 1) == 0 )
    {
      v74 = *(_DWORD *)(v73 + 1512);
      v121 = v74 == 5;
      if ( v74 != 5 )
      {
        flOldProtect[17] = dword_10317A9FC;
        if ( (dword_10317A9FC & 0x20) == 0 )
          DBMgr::StartupUserDatabases(qword_10316ECA0);
      }
    }
  }
  StartUp::WaitForTempDbReady(0);
  dword_10316ECB0 |= 0x400u;
  EventManualInternal<SuspendQueueSLock>::Signal(&StartUp::sm_UserDBsReady, 0);
  qword_1033C1280();
  if ( (unsigned int)IsContainedAGEnabledInstance() )
    StartupDependencies::SetAsCompleted(17);
  if ( (unsigned int)IsReplicatedMasterEnabled() )
  {
    v263 = &word_103185B6E;
    if ( !word_103185B6E )
      StartupDependencies::WaitForDone(17);
  }
  flOldProtect[18] = dword_10317A9FC;
  if ( (dword_10317A9FC & 4) == 0 || dword_1031852C8 )
  {
    if ( (unsigned int)IsContainedAGEnabledInstance() )
    {
      v82 = *(_DWORD *)CDefaultCollation::PDCServer();
      v107 = 256;
      if ( !FGetCollationName(v82, v286, &v107) )
      {
        v269 = 0;
        v286[0] = 0;
        v107 = 0;
      }
      v171 = *(_DWORD *)(g_dbtableFactory[4](32762) + 2244);
      if ( v82 != v171 && !FRecollateDB(0x7FFAu, v82, 3u, 0, 1, 0, 0, 0) )
      {
        v270 = L"model_replicatedmaster";
        v172 = dword_1031C47E8;
        LODWORD(v101) = v107;
        scierrlog(0x12u, 6, 25, 2, (unsigned __int64)(int)dword_1031C47E8 >> 1, L"model_replicatedmaster", v101, v286);
      }
      v80 = *(unsigned int *)(g_dbtableFactory[4](32761) + 2244);
      v173 = v80;
      if ( v82 != (_DWORD)v80 && !FRecollateDB(0x7FF9u, v82, 3u, 0, 1, 0, 0, 0) )
      {
        v271 = L"model_msdb";
        v174 = dword_1031C47EC;
        LODWORD(v102) = v107;
        scierrlog(0x12u, 6, 25, 3, (unsigned __int64)(int)dword_1031C47EC >> 1, L"model_msdb", v102, v286);
      }
    }
  }
  else
  {
    v264 = SOS_OS_OsInfo;
    if ( OsInfo::IsXPlatInstance(SOS_OS_OsInfo) )
    {
      v122 = BYTE3(qword_10317B10F) >> 4;
      if ( (qword_10317B10F & 0x10000000) == 0 )
      {
        DefaultLocale = GetDefaultLocale();
        LODWORD(v100) = 49958;
        v76 = StringCchPrintf_lW(
                v289,
                0x800u,
                L"DECLARE @UserDatabaseCount INT = (SELECT COUNT (*) FROM master.sys.databases WHERE name NOT IN ('master'"
                 ", 'model', 'msdb', 'tempdb')) IF (@UserDatabaseCount > 0) BEGIN \tRAISERROR(%ld, -1, -1) WITH LOG END ",
                DefaultLocale,
                v100);
        CheckHrFailAndExit(v76, "String format error while verifying no user databases attached");
        v77 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v78 = *(_QWORD *)(v77 + 256);
        if ( !v78 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v78 = *(_QWORD *)(v77 + 256);
        }
        ExecSql = CreateExecSql(*(struct IMemObj **)(v78 + 1000), 0);
        v265 = ExecSql;
        if ( !ExecSql )
          utassert_fail(1u, "pExecSql", "\"sql\\\\ntdbms\\\\storeng\\\\dfs\\\\startup\\\\startup.cpp\"", 5644, 0);
        (*(void (__fastcall **)(struct IExecSql *))(*(_QWORD *)ExecSql + 48LL))(ExecSql);
        if ( !(*(unsigned int (__fastcall **)(struct IExecSql *, wchar_t *, _QWORD))(*(_QWORD *)ExecSql + 8LL))(
                ExecSql,
                v289,
                0) )
        {
          WriteConsoleMessage(0xC326u);
          SQLExit(14);
        }
        v266 = ExecSql;
        (*(void (__fastcall **)(struct IExecSql *, __int64))(*(_QWORD *)ExecSql + 224LL))(ExecSql, 1);
      }
    }
    dword_10316ECB0 |= 0x10u;
    if ( (unsigned int)IsReplicatedMasterEnabled() )
    {
      v198 = &word_103185B6E;
      if ( !word_103185B6E )
        ExitModelMsdbFromReadOnly();
    }
    v198 = 0;
    RecollateServer(cidNew, 0);
    if ( (unsigned int)IsReplicatedMasterEnabled() )
    {
      v268 = &word_103185B6E;
      if ( !word_103185B6E )
        SetModelMsdbToReadOnly();
    }
  }
  v123 = byte_10317AD43;
  if ( (byte_10317AD43 & 1) == 0 )
  {
    if ( *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v81, v80) + 1236) )
      v124 = 1;
    else
      qword_1033C1278();
  }
  dword_10316ECB0 |= 0x10u;
  if ( (*v48 & 0x20) != 0 )
  {
    if ( *((_DWORD *)s_pServerConf + 3) == 1 )
      VersionCopyDowngradeScript();
    v133 = 0;
    v272 = 0;
    try
    {
      ExcHandler::ExcHandler((ExcHandler *)v284, 0, 0, 0, NoThrowHandler, 0);
      Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v203, 1);
      v133 = DBTABLE::UpgradeDatabaseScripts(v140);
      v273 = v204;
      v175 = ~v203;
      *(_DWORD *)(v204 + 616) &= ~v203;
      ExcHandler::~ExcHandler((ExcHandler *)v284);
    }
    catch ( SQLError v283 )
    {
      try
      {
        ExceptionBackout::ExceptionBackout((ExceptionBackout *)v205, (const struct SQLError *)v283);
        CurrentException = ExceptionBackout::GetCurrentException((ExceptionBackout *)v205);
        ExceptionRethrow(CurrentException);
        ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v205);
      }
      catch ( ShortStackException )
      {
      }
    }
    v83 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v84 = *(struct Worker **)(v83 + 256);
    if ( !v84 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v84 = *(struct Worker **)(v83 + 256);
    }
    v274 = v84;
    if ( *((_DWORD *)v84 + 139) )
      ExceptionPostCatchActions(v84);
    if ( !v133 )
      ex_raise(34, 17, 21, 3);
  }
  if ( v49 && (unsigned int)(*((_DWORD *)s_pServerConf + 3) - 1) > 1 )
  {
    dword_10316ECB0 &= ~0x2000u;
    StartupDependencies::SetAsCompleted(10);
  }
  if ( (unsigned int)(*((_DWORD *)s_pServerConf + 3) - 1) <= 1 )
  {
    v176 = dword_10317A9FC;
    if ( (dword_10317A9FC & 1) == 0 )
    {
      v85 = dword_1031C47D0;
      v86 = GetMasterDbId();
      OfficeLockdown(v86, L"master", v85);
    }
    dword_10316ECB0 &= ~0x2000u;
    StartupDependencies::SetAsCompleted(10);
  }
  v125 = (unsigned __int8)byte_10317AD42 >> 7;
  if ( byte_10317AD42 >= 0 )
  {
    v126 = byte_10317AD43;
    if ( (byte_10317AD43 & 1) == 0 )
    {
      v275 = SOS_OS_OsInfo;
      if ( !OsInfo::IsLinux(SOS_OS_OsInfo)
        || *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v88, v87) + 537)
        || (CPolybaseFeatureManager::MaybeInitExecPaths(&g_PolybaseFeatureManager), !qword_1031D6150)
        || CPolybaseFeatureManager::IsPolybaseProvisioned((CPolybaseFeatureManager *)&g_PolybaseFeatureManager, 1) )
      {
        v89 = 0;
      }
      else
      {
        dword_10316ECB0 |= 0x2000u;
        StartUp::RunPolyBaseProvisioningScripts(v140);
        dword_10316ECB0 &= ~0x2000u;
        v89 = 1;
      }
      v127 = v89;
      if ( !*(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v88, v87) + 537) )
      {
        CPolybaseFeatureManager::MaybeInitExecPaths(&g_PolybaseFeatureManager);
        if ( qword_1031D6150 )
        {
          if ( (unsigned int)IsReplicatedMasterEnabled() ? byte_103179135 : *((_BYTE *)GetServerConfiguration() + 13645) )
            CPolybaseFeatureManager::EnablePolybase(&g_PolybaseFeatureManager);
        }
      }
      v199 = SOS_OS_OsInfo;
      if ( (OsInfo::IsWindows(SOS_OS_OsInfo) || byte_10317AB00)
        && CPolybaseFeatureManager::IsPolybaseProvisioned((CPolybaseFeatureManager *)&g_PolybaseFeatureManager, 1) )
      {
        qword_1033C12D0();
      }
    }
  }
  v128 = byte_1031852E4;
  if ( byte_1031852E4 )
  {
    CFidoGLMManager = GetCFidoGLMManager();
    (**(void (__fastcall ***)(struct CFidoGLMManager *))CFidoGLMManager)(CFidoGLMManager);
    started = StartFidoClients();
    if ( started < 0 )
    {
      _mm_lfence();
      scierrlog(0x575Du, (unsigned int)started);
      if ( started != -2147017783 )
      {
        if ( dword_103172528 )
          SQLExit(16);
      }
    }
  }
  StartupDependencies::SetAsCompleted(8);
  if ( dword_103172574 )
  {
    v132 = 0;
    v94 = getdbid(L"sbs", 6, &v132, 0);
    log_unlocalized(L"Orca: '%ls' exists? : '%d'.", L"sbs", v94);
    if ( !v94 )
      utassert_fail(1u, "dbExist", "\"sql\\\\ntdbms\\\\storeng\\\\dfs\\\\startup\\\\startup.cpp\"", 5906, 0);
    v95 = v132;
    log_unlocalized_systemmetadata(L"Orca: SBS dbid = '%lu'", v132);
    if ( !v95 )
      utassert_fail(
        1u,
        "sbsDbId != x_MDDatabaseIdBad",
        "\"sql\\\\ntdbms\\\\storeng\\\\dfs\\\\startup\\\\startup.cpp\"",
        5909,
        0);
    log_unlocalized_systemmetadata(L"%ls", L"Orca: Register SBS IO functions and their addresses in the registry.");
    RegisterSbsDetourFunction();
    log_unlocalized(L"Orca: SBS IO registration done. Now signal '%ls' semaphore.", L"FileServiceReady");
    dword_10317252C = 1;
    PrepareBeforeSignalSbs();
    SignalSbsDetourDll();
    log_unlocalized(L"Orca: '%ls' semaphore signalled successfully.", L"FileServiceReady");
  }
  if ( byte_1031852E4 && (byte_10316E8AD || (qword_10317B171 & 0x200) != 0) && dword_103172528 )
  {
    InitFidoIndexStorePmo();
    StartFidoIndexStoreClient();
  }
  if ( (byte_10316E5F0 || (qword_10317B06A & 0x2000000000LL) != 0)
    && (*(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance(v93, v92) + 1153) || (byte_10317B062 & 0x40) != 0)
    && (byte_10316E5F3 || (byte_10317B064 & 0x20) != 0) )
  {
    v199 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset);
    StartUp::WaitForTempDbReady(v199);
    NativeShuffleHelper::EnableFileStreamForTempDb();
  }
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                    + SystemThread_TlsOffset
                                    + 8LL)
                        + 96LL)
            + 1456LL) = v146;
  AutoReadOnlyIMA::~AutoReadOnlyIMA((AutoReadOnlyIMA *)&v135);
  AutoDbLock::~AutoDbLock((AutoDbLock *)v169);
  ExcHandler::~ExcHandler((ExcHandler *)v282);
  v96 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v97 = *(struct Worker **)(v96 + 256);
  if ( !v97 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v97 = *(struct Worker **)(v96 + 256);
  }
  if ( *((_DWORD *)v97 + 139) )
    ExceptionPostCatchActions(v97);
}

```

## disassembly

```asm
0x101b9b590  push    r13
0x101b9b592  push    r14
0x101b9b594  push    r15
0x101b9b596  mov     eax, 1B50h
0x101b9b59b  call    _alloca_probe
0x101b9b5a0  sub     rsp, rax
0x101b9b5a3  mov     [rsp+1B68h+var_16F0], 0FFFFFFFFFFFFFFFEh
0x101b9b5af  mov     [rsp+1B68h+arg_0], rbx
0x101b9b5b7  mov     [rsp+1B68h+arg_8], rsi
0x101b9b5bf  mov     [rsp+1B68h+arg_10], rdi
0x101b9b5c7  mov     [rsp+1B68h+arg_18], r12
0x101b9b5cf  mov     rax, cs:__security_cookie
0x101b9b5d6  xor     rax, rsp
0x101b9b5d9  mov     [rsp+1B68h+var_28], rax
0x101b9b5e1  mov     rdi, rcx
0x101b9b5e4  xor     ebx, ebx
0x101b9b5e6  mov     [rsp+1B68h+var_1B20], rbx
0x101b9b5eb  mov     [rsp+1B68h+var_1A08], rbx
0x101b9b5f3  mov     eax, cs:dword_10317A9FC
0x101b9b5f9  test    al, 1
0x101b9b5fb  jz      short loc_101B9B61E
0x101b9b5fd  or      cs:dword_10316ECB0, 1
0x101b9b604  mov     ecx, 44F8h; unsigned int
0x101b9b609  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x101b9b60e  mov     ecx, 44FAh; unsigned int
0x101b9b613  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x101b9b618  mov     eax, cs:dword_10317A9FC
0x101b9b61e  test    al, 4
0x101b9b620  jz      short loc_101B9B639
0x101b9b622  or      cs:dword_10316ECB0, 1000h
0x101b9b62c  call    cs:__imp_?GetTdsHandle@@YAPEAUtds_handle@@XZ; GetTdsHandle(void)
0x101b9b632  mov     byte ptr [rax+210h], 1
0x101b9b639  xor     ecx, ecx
0x101b9b63b  call    cs:qword_1033C1298
0x101b9b641  test    eax, eax
0x101b9b643  jnz     short loc_101B9B667
0x101b9b645  lea     rdx, aOpendbsandreco_0; "OpenDBsAndRecover(), SetSecuritySA"
0x101b9b64c  mov     ecx, 42E0h; unsigned int
0x101b9b651  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x101b9b656  xor     edx, edx
0x101b9b658  lea     ecx, [rdx+4]
0x101b9b65b  mov     r8d, 42Ah
0x101b9b661  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x101b9b667  test    cs:byte_10317AD42, 80h
0x101b9b66e  jz      short loc_101B9B677
0x101b9b670  mov     ecx, 44FCh
0x101b9b675  jmp     short loc_101B9B692
0x101b9b677  movzx   eax, cs:byte_10317AD43
0x101b9b67e  test    al, 1
0x101b9b680  jz      short loc_101B9B689
0x101b9b682  mov     ecx, 0D4Bh
0x101b9b687  jmp     short loc_101B9B692
0x101b9b689  test    al, 2
0x101b9b68b  jz      short loc_101B9B698
0x101b9b68d  mov     ecx, 44FDh; unsigned int
0x101b9b692  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x101b9b697  nop
0x101b9b698  xor     edx, edx; unsigned __int16
0x101b9b69a  mov     [rsp+1B68h+var_1B40], rbx; struct Worker *
0x101b9b69f  lea     rax, ?HandleAndNoteToErrorlog@@YAHHHHHPEAD@Z; HandleAndNoteToErrorlog(int,int,int,int,char *)
0x101b9b6a6  mov     [rsp+1B68h+var_1B48], rax; int (*)(int, int, int, int, char *)
0x101b9b6ab  xor     r9d, r9d; unsigned __int8
0x101b9b6ae  xor     r8d, r8d; unsigned __int8
0x101b9b6b1  lea     rcx, [rsp+1B68h+var_15F0]; this
0x101b9b6b9  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x101b9b6be  nop
0x101b9b6bf  lea     r8, qword_1031720D0
0x101b9b6c6  lea     rdx, qword_1031720C8
0x101b9b6cd  mov     rcx, cs:__imp_?g_pmoGlobal@@3PEAVIMemObj@@EA; IMemObj * g_pmoGlobal
0x101b9b6d4  mov     rcx, [rcx]
0x101b9b6d7  call    cs:qword_1033C1290
0x101b9b6dd  mov     rcx, cs:__imp_?g_pmoGlobal@@3PEAVIMemObj@@EA; IMemObj * g_pmoGlobal
0x101b9b6e4  mov     rcx, [rcx]
0x101b9b6e7  call    cs:qword_1033C12B0
0x101b9b6ed  mov     cs:qword_1031720D8, rax
0x101b9b6f4  movzx   eax, cs:byte_10317AD42
0x101b9b6fb  shr     al, 7
0x101b9b6fe  mov     [rsp+1B68h+var_1AFB], al
0x101b9b702  test    al, al
0x101b9b704  jnz     loc_101B9C141
0x101b9b70a  movzx   eax, cs:byte_10317AD43
0x101b9b711  mov     [rsp+1B68h+var_1AF4], al
0x101b9b715  test    al, 1
0x101b9b717  jnz     loc_101B9C141
0x101b9b71d  mov     [rsp+1B68h+var_1B48], 0FFFFFFFFFFFFFFFFh
0x101b9b726  lea     r9, [rsp+1B68h+var_1A08]
0x101b9b72e  xor     r8d, r8d
0x101b9b731  xor     edx, edx
0x101b9b733  lea     rcx, ?StartModelAndTempdb@StartUp@@SAPEAXPEAX@Z; StartUp::StartModelAndTempdb(void *)
0x101b9b73a  call    cs:__imp_?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z; SOS_OS::EnqueueTask(void * (*)(void *),void *,ulong,SOS_Task * *,unsigned __int64)
0x101b9b740  test    eax, eax
0x101b9b742  jz      short loc_101B9B770
0x101b9b744  lea     rdx, aStartModelTemp; "start model tempdb"
0x101b9b74b  mov     ecx, 42E0h; unsigned int
0x101b9b750  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x101b9b755  mov     edx, 42E0h
0x101b9b75a  mov     ecx, 5
0x101b9b75f  mov     r8d, 42Ah
0x101b9b765  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x101b9b76b  jmp     loc_101B9C15B
0x101b9b770  mov     rdx, [rsp+1B68h+var_1A08]
0x101b9b778  add     rdx, 10h
0x101b9b77c  mov     [rsp+1B68h+var_1940], rdx
0x101b9b784  mov     eax, 0FFFFFFFFh
0x101b9b789  lock xadd [rdx+18h], eax
0x101b9b78e  sub     eax, 1
0x101b9b791  mov     [rsp+1B68h+var_18F0], eax
0x101b9b798  mov     [rsp+1B68h+var_18EC], eax
0x101b9b79f  jnz     loc_101B9C15B
0x101b9b7a5  mov     rcx, [rsp+1B68h+var_1940]
0x101b9b7ad  cmp     qword ptr [rcx+8], 0
0x101b9b7b2  jz      short loc_101B9B7BE
0x101b9b7b4  call    ?RemoveAndDestroy@?$TListElem@V?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@@@IEAAXXZ; TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(void)
0x101b9b7b9  jmp     loc_101B9C15B
0x101b9b7be  test    rdx, rdx
0x101b9b7c1  lea     rax, [rdx-10h]
0x101b9b7c5  jnz     short loc_101B9B7CA
0x101b9b7c7  mov     rax, rbx
0x101b9b7ca  mov     [rsp+1B68h+var_1AE8], rax
0x101b9b7d2  add     rax, 0B8h
0x101b9b7d8  mov     [rsp+1B68h+var_16A0], rax
0x101b9b7e0  mov     eax, [rax]
0x101b9b7e2  cmp     eax, 2
0x101b9b7e5  jnz     loc_101B9BB10
0x101b9b7eb  mov     rax, [rsp+1B68h+var_1AE8]
0x101b9b7f3  mov     rcx, [rax+0A0h]
0x101b9b7fa  mov     [rsp+1B68h+var_1678], rcx
0x101b9b802  add     rcx, 1358h
0x101b9b809  mov     [rsp+1B68h+var_1A28], rcx
0x101b9b811  mov     [rsp+1B68h+var_1A20], ebx
0x101b9b818  mov     [rsp+1B68h+var_1630], rcx
0x101b9b820  mov     [rsp+1B68h+var_1628], rbx
0x101b9b828  mov     [rsp+1B68h+var_1600], rbx
0x101b9b830  mov     [rsp+1B68h+var_1A40], rbx
0x101b9b838  mov     [rsp+1B68h+var_1A50], rbx
0x101b9b840  mov     eax, gs:48h
0x101b9b848  mov     ecx, eax
0x101b9b84a  mov     [rsp+1B68h+var_1A58], rcx
0x101b9b852  mov     [rsp+1B68h+var_1890], 100h
0x101b9b85d  mov     rax, [rsp+1B68h+var_1A28]
0x101b9b865  mov     [rsp+1B68h+var_15F8], rax
0x101b9b86d  mov     eax, [rax]
0x101b9b86f  test    eax, eax
0x101b9b871  jnz     short loc_101B9B8AF
0x101b9b873  mov     rdx, [rsp+1B68h+var_1A58]
0x101b9b87b  mov     rcx, [rsp+1B68h+var_1A28]
0x101b9b883  xor     eax, eax
0x101b9b885  lock cmpxchg [rcx], rdx
0x101b9b88a  mov     [rsp+1B68h+var_1620], rax
0x101b9b892  mov     [rsp+1B68h+var_1618], rax
0x101b9b89a  mov     eax, ebx
0x101b9b89c  setz    al
0x101b9b89f  mov     [rsp+1B68h+var_1A70], eax
0x101b9b8a6  test    eax, eax
0x101b9b8a8  jz      short loc_101B9B8B6
0x101b9b8aa  jmp     loc_101B9BACB
0x101b9b8af  mov     [rsp+1B68h+var_1A70], ebx
0x101b9b8b6  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x101b9b8bd  mov     ecx, [rax]
0x101b9b8bf  and     ecx, 84h
0x101b9b8c5  cmp     cl, 84h
0x101b9b8c8  jnz     short loc_101B9B923
0x101b9b8ca  mov     [rsp+1B68h+var_188C], 58h ; 'X'
0x101b9b8d5  mov     r8, gs:58h
0x101b9b8de  mov     [rsp+1B68h+var_1860], r8
0x101b9b8e6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101b9b8ed  mov     edx, [rax]
0x101b9b8ef  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101b9b8f6  mov     ecx, [rax]
0x101b9b8f8  mov     rsi, [r8+rdx*8]
0x101b9b8fc  add     rsi, rcx
0x101b9b8ff  mov     [rsp+1B68h+var_1858], rsi
0x101b9b907  jz      short loc_101B9B923
0x101b9b909  cmp     [rsi+110h], rsi
0x101b9b910  jnz     short loc_101B9B923
0x101b9b912  mov     rsi, [rsi+100h]
0x101b9b919  mov     [rsp+1B68h+var_1850], rsi
0x101b9b921  jmp     short loc_101B9B926
0x101b9b923  mov     rsi, rbx
0x101b9b926  mov     [rsp+1B68h+var_1A50], rsi
0x101b9b92e  test    rsi, rsi
0x101b9b931  jz      short loc_101B9B9AE
0x101b9b933  lea     rax, [rsp+1B68h+var_1A00]
0x101b9b93b  mov     [rsp+1B68h+var_1848], rax
0x101b9b943  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x101b9b94a  mov     ecx, [rax]
0x101b9b94c  mov     [rsp+1B68h+var_1888], ecx
0x101b9b953  test    ecx, ecx
0x101b9b955  jz      short loc_101B9B97E
0x101b9b957  lea     rcx, [rsp+1B68h+PerformanceCount]; lpPerformanceCount
0x101b9b95f  call    cs:__imp_QueryPerformanceCounter
0x101b9b965  mov     [rsp+1B68h+var_19E0], eax
0x101b9b96c  mov     rax, qword ptr [rsp+1B68h+PerformanceCount]
0x101b9b974  mov     [rsp+1B68h+var_1A00], rax
0x101b9b97c  jmp     short loc_101B9B99E
0x101b9b97e  mov     rax, ds:7FFE0008h
0x101b9b986  mov     [rsp+1B68h+var_1930], rax
0x101b9b98e  mov     [rsp+1B68h+var_1A00], rax
0x101b9b996  mov     rsi, [rsp+1B68h+var_1A50]
0x101b9b99e  mov     [rsp+1B68h+var_1840], rax
0x101b9b9a6  mov     [rsp+1B68h+var_1A40], rax
0x101b9b9ae  mov     [rsp+1B68h+var_19DC], 2
0x101b9b9b9  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x101b9b9c0  mov     rcx, [rsp+1B68h+var_1A28]
0x101b9b9c8  cmp     byte ptr [rax+0C7h], 0
0x101b9b9cf  jge     short loc_101B9B9E3
0x101b9b9d1  mov     r8, [rsp+1B68h+var_1A58]
0x101b9b9d9  mov     rdx, rsi
0x101b9b9dc  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x101b9b9e1  jmp     short loc_101B9B9F0
0x101b9b9e3  mov     rdx, [rsp+1B68h+var_1A58]
0x101b9b9eb  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x101b9b9f0  test    rsi, rsi
0x101b9b9f3  jz      loc_101B9BACB
0x101b9b9f9  lea     rax, [rsp+1B68h+var_1A48]
0x101b9ba01  mov     [rsp+1B68h+var_1838], rax
0x101b9ba09  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x101b9ba10  mov     ecx, [rax]
0x101b9ba12  mov     [rsp+1B68h+var_19D8], ecx
0x101b9ba19  test    ecx, ecx
0x101b9ba1b  jz      short loc_101B9BA44
0x101b9ba1d  lea     rcx, [rsp+1B68h+var_1928]; lpPerformanceCount
0x101b9ba25  call    cs:__imp_QueryPerformanceCounter
0x101b9ba2b  mov     [rsp+1B68h+var_19D4], eax
0x101b9ba32  mov     rax, qword ptr [rsp+1B68h+var_1928]
0x101b9ba3a  mov     [rsp+1B68h+var_1A48], rax
0x101b9ba42  jmp     short loc_101B9BA64
0x101b9ba44  mov     rax, ds:7FFE0008h
0x101b9ba4c  mov     [rsp+1B68h+var_1920], rax
0x101b9ba54  mov     [rsp+1B68h+var_1A48], rax
0x101b9ba5c  mov     rsi, [rsp+1B68h+var_1A50]
0x101b9ba64  lea     rcx, [rsp+1B68h+var_1A40]
0x101b9ba6c  mov     [rsp+1B68h+var_1830], rcx
0x101b9ba74  lea     rcx, [rsp+1B68h+var_1A48]
0x101b9ba7c  mov     [rsp+1B68h+var_1828], rcx
0x101b9ba84  mov     rcx, [rsp+1B68h+var_1A40]
0x101b9ba8c  cmp     rax, rcx
0x101b9ba8f  jb      short loc_101B9BA9E
0x101b9ba91  sub     rax, rcx
0x101b9ba94  mov     [rsp+1B68h+var_1AC8], rax
0x101b9ba9c  jmp     short loc_101B9BAA9
0x101b9ba9e  mov     rax, rbx
0x101b9baa1  mov     [rsp+1B68h+var_1AC8], rbx
0x101b9baa9  mov     [rsp+1B68h+var_1A10], rax
0x101b9bab1  mov     [rsp+1B68h+var_1820], rax
0x101b9bab9  lea     rcx, [rsi+0C78h]
0x101b9bac0  mov     [rsp+1B68h+var_1818], rcx
0x101b9bac8  add     [rcx], rax
0x101b9bacb  mov     [rsp+1B68h+var_1A20], 1
0x101b9bad6  mov     rdx, [rsp+1B68h+var_1AE8]
0x101b9bade  mov     rcx, [rdx+8]
0x101b9bae2  mov     [rsp+1B68h+var_1810], rcx
0x101b9baea  mov     rax, [rdx]
0x101b9baed  mov     [rsp+1B68h+var_1808], rax
0x101b9baf5  mov     [rax+8], rcx
0x101b9baf9  mov     [rcx], rax
0x101b9bafc  mov     [rdx+8], rbx
0x101b9bb00  mov     [rdx], rbx
0x101b9bb03  lea     rcx, [rsp+1B68h+var_1A28]
0x101b9bb0b  call    ??1?$SpinlockHolder@$0L@$01$0BAAAABAC@@@QEAA@XZ; SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(void)
0x101b9bb10  mov     [rsp+1B68h+var_1AC8], rbx
0x101b9bb18  mov     [rsp+1B68h+var_19D0], 58h ; 'X'
0x101b9bb23  mov     r8, gs:58h
0x101b9bb2c  mov     [rsp+1B68h+var_1800], r8
0x101b9bb34  mov     rax, cs:__imp_SystemThread_TlsIndex
0x101b9bb3b  mov     edx, [rax]
0x101b9bb3d  mov     rax, cs:__imp_SystemThread_TlsOffset
0x101b9bb44  mov     ecx, [rax]
0x101b9bb46  mov     rdx, [r8+rdx*8]
0x101b9bb4a  add     rdx, rcx
0x101b9bb4d  mov     [rsp+1B68h+var_17F8], rdx
0x101b9bb55  jz      short loc_101B9BBA5
0x101b9bb57  cmp     [rdx+110h], rdx
0x101b9bb5e  jnz     short loc_101B9BBA5
0x101b9bb60  mov     rax, [rdx+100h]
0x101b9bb67  mov     [rsp+1B68h+var_1AC8], rax
0x101b9bb6f  mov     [rsp+1B68h+var_1918], rax
0x101b9bb77  mov     rsi, [rsp+1B68h+var_1AE8]
0x101b9bb7f  test    rax, rax
0x101b9bb82  jz      short loc_101B9BBBD
0x101b9bb84  cmp     [rax+210h], rsi
0x101b9bb8b  jnz     short loc_101B9BBBD
0x101b9bb8d  test    rsi, rsi
0x101b9bb90  lea     rcx, [rsi-8]
0x101b9bb94  jnz     short loc_101B9BB99
0x101b9bb96  mov     rcx, rbx; this
0x101b9bb99  xor     edx, edx; unsigned int
0x101b9bb9b  call    ??_GISOSHost_TaskImpl@@IEAAPEAXI@Z; ISOSHost_TaskImpl::`scalar deleting destructor'(uint)
0x101b9bba0  jmp     loc_101B9C15B
0x101b9bba5  mov     rax, [rsp+1B68h+var_1AC8]
0x101b9bbad  mov     [rsp+1B68h+var_1918], rax
0x101b9bbb5  mov     rsi, [rsp+1B68h+var_1AE8]
0x101b9bbbd  mov     rcx, [rsi+0A8h]
0x101b9bbc4  test    rcx, rcx
0x101b9bbc7  jz      loc_101B9C10D
0x101b9bbcd  cmp     qword ptr [rcx+0F0h], 0
0x101b9bbd5  jz      loc_101B9C10D
0x101b9bbdb  call    cs:__imp_?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ; SOS_Node::IsTaskStoreDisabled(void)
0x101b9bbe1  test    al, al
0x101b9bbe3  jnz     loc_101B9C10D
  ... truncated ...
```

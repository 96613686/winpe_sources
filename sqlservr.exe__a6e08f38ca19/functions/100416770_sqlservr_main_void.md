# sqlservr_main(void)

- ea: `0x100416770`
- end: `0x1004187c6`
- name: `?sqlservr_main@@YAXXZ`
- size: `8278`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `55`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x10040b120`
- `0x10040b330`

## callees

- `0x100401580`
- `0x100401800`
- `0x100401aa0`
- `0x100402080`
- `0x100402ec0`
- `0x100404a30`
- `0x100407030`
- `0x100408320`
- `0x100408560`
- `0x100408810`
- `0x100409cb0`
- `0x10040b2b0`
- `0x10040b7c0`
- `0x10040e370`
- `0x10040e6d0`
- `0x1004115f0`
- `0x100412470`
- `0x100413d90`
- `0x1004161b0`
- `0x1004162d0`
- `0x100416770`
- `0x100419a20`
- `0x100419c70`
- `0x100419fd0`
- `0x10041d870`
- `0x10041df30`
- `0x10041e170`
- `0x10041e420`
- `0x10041e540`
- `0x10041e640`
- `0x10041eac0`
- `0x100420700`
- `0x1004231d0`
- `0x1004233a0`
- `0x100423500`
- `0x100423970`
- `0x100424980`
- `0x100425030`
- `0x100438200`
- `0x1004382f0`
- `0x100439330`
- `0x10043a570`
- `0x10043cc10`
- `0x10043ce60`
- `0x1004403d0`
- `0x100440760`
- `0x100440860`
- `0x100440a70`
- `0x100448470`
- `0x100448530`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x1004169b8`
- `KERNEL32!WaitForSingleObject` at `0x1004169b8`
- `KERNEL32!Sleep` at `0x1004171ac`
- `KERNEL32!Sleep` at `0x1004171ac`
- `KERNEL32!CreateFileMappingW` at `0x100417ab8`
- `KERNEL32!CreateFileMappingW` at `0x100417ab8`
- `KERNEL32!MapViewOfFile` at `0x100417ae5`
- `KERNEL32!MapViewOfFile` at `0x100417ae5`
- `KERNEL32!LoadLibraryW` at `0x100417b94`
- `KERNEL32!LoadLibraryW` at `0x100417b94`
- `KERNEL32!GetProcAddress` at `0x100417ba9`
- `KERNEL32!GetProcAddress` at `0x100417ba9`
- `KERNEL32!SetEnvironmentVariableW` at `0x100416808`
- `KERNEL32!SetEnvironmentVariableW` at `0x100416808`
- `KERNEL32!VirtualProtect` at `0x10041856e`
- `KERNEL32!VirtualProtect` at `0x10041856e`
- `KERNEL32!CreateEventW` at `0x10041689e`
- `KERNEL32!CreateEventW` at `0x10041689e`
- `KERNEL32!CreateThread` at `0x10041692b`
- `KERNEL32!CreateThread` at `0x10041692b`
- `KERNEL32!IsDebuggerPresent` at `0x10041719b`
- `KERNEL32!IsDebuggerPresent` at `0x1004171b4`
- `KERNEL32!IsDebuggerPresent` at `0x10041719b`
- `KERNEL32!IsDebuggerPresent` at `0x1004171b4`
- `KERNEL32!GetActiveProcessorGroupCount` at `0x1004176e6`
- `KERNEL32!GetActiveProcessorGroupCount` at `0x1004176e6`
- `KERNEL32!GetEnvironmentVariableW` at `0x100416eac`
- `KERNEL32!GetEnvironmentVariableW` at `0x100416eac`
- `KERNEL32!CloseHandle` at `0x1004169aa`
- `KERNEL32!CloseHandle` at `0x1004169c1`
- `KERNEL32!CloseHandle` at `0x100417af8`
- `KERNEL32!CloseHandle` at `0x1004169aa`
- `KERNEL32!CloseHandle` at `0x1004169c1`
- `KERNEL32!CloseHandle` at `0x100417af8`
- `KERNEL32!GetLastError` at `0x1004168ac`
- `KERNEL32!GetLastError` at `0x100416936`
- `KERNEL32!GetLastError` at `0x100417ac6`
- `KERNEL32!GetLastError` at `0x100417bbb`
- `KERNEL32!GetLastError` at `0x1004168ac`
- `KERNEL32!GetLastError` at `0x100416936`
- `KERNEL32!GetLastError` at `0x100417ac6`
- `KERNEL32!GetLastError` at `0x100417bbb`
- `KERNEL32!QueryPerformanceCounter` at `0x1004181b0`
- `KERNEL32!QueryPerformanceCounter` at `0x100418201`
- `KERNEL32!QueryPerformanceCounter` at `0x100418497`
- `KERNEL32!QueryPerformanceCounter` at `0x1004184e9`
- `KERNEL32!QueryPerformanceCounter` at `0x1004181b0`
- `KERNEL32!QueryPerformanceCounter` at `0x100418201`
- `KERNEL32!QueryPerformanceCounter` at `0x100418497`
- `KERNEL32!QueryPerformanceCounter` at `0x1004184e9`
- `KERNEL32!VirtualFree` at `0x1004186c1`
- `KERNEL32!VirtualFree` at `0x1004186c1`
- `sqlmin!?RegisterSqlClusterInstance@FClusMgr@@SAXXZ` at `0x1004174d3`
- `sqlmin!?RegisterSqlClusterInstance@FClusMgr@@SAXXZ` at `0x1004174d3`
- `sqlmin!?SetupNamedObjectSecurity@StartUp@@SAXXZ` at `0x100416ecf`
- `sqlmin!?SetupNamedObjectSecurity@StartUp@@SAXXZ` at `0x100416ecf`
- `sqlmin!?GetPropertyBagStart@InstanceConfigStoreManager@@QEAAJXZ` at `0x100416b49`
- `sqlmin!?GetPropertyBagStart@InstanceConfigStoreManager@@QEAAJXZ` at `0x100416b49`
- `sqlmin!?StaticInit@InstanceConfigStoreManager@@SAJPEAVIRgIsolationSettingsUpdater@@@Z` at `0x100416ae5`
- `sqlmin!?StaticInit@InstanceConfigStoreManager@@SAJPEAVIRgIsolationSettingsUpdater@@@Z` at `0x100416ae5`
- `sqlmin!?BlobAccess_FileSystemInit@@YA_NXZ` at `0x100417b39`
- `sqlmin!?BlobAccess_FileSystemInit@@YA_NXZ` at `0x100417b39`
- `sqlmin!?GetPropertyBagComplete@InstanceConfigStoreManager@@QEAAJK@Z` at `0x100417c06`
- `sqlmin!?GetPropertyBagComplete@InstanceConfigStoreManager@@QEAAJK@Z` at `0x100417c06`
- `sqlmin!?ParsePropertyBagStartup@InstanceConfigStoreManager@@QEAAXXZ` at `0x100417c23`
- `sqlmin!?ParsePropertyBagStartup@InstanceConfigStoreManager@@QEAAXXZ` at `0x100417c23`
- `sqlmin!?InitFCIMembership@RESOURCE@@QEAAXXZ` at `0x100417d77`
- `sqlmin!?InitFCIMembership@RESOURCE@@QEAAXXZ` at `0x100417d77`
- `sqlmin!?InitSqlVdi@RESOURCE@@QEAAXXZ` at `0x100417d84`
- `sqlmin!?InitSqlVdi@RESOURCE@@QEAAXXZ` at `0x100417d84`
- `sqlmin!?InitializeCallbacks@StartUp@@SAXXZ` at `0x100417d9b`
- `sqlmin!?InitializeCallbacks@StartUp@@SAXXZ` at `0x100417d9b`
- `sqlmin!?WaitForMasterDbReady@StartUp@@SAXXZ` at `0x100417f65`
- `sqlmin!?WaitForMasterDbReady@StartUp@@SAXXZ` at `0x100417f65`
- `sqlmin!?InitializeInstanceConfigStoreManagerCallback@InstanceConfigStoreManager@@SAXPEB_W00PEAX@Z` at `0x100417f9b`
- `sqlmin!?InitializeInstanceConfigStoreManagerCallback@InstanceConfigStoreManager@@SAXPEB_W00PEAX@Z` at `0x100417fd3`
- `sqlmin!?InitControl@RESOURCE@@QEAAXXZ` at `0x1004176c7`
- `sqlmin!?InitControl@RESOURCE@@QEAAXXZ` at `0x1004176c7`
- `sqlmin!?StaticInit@InstanceHistoryStoreManager@@SAJXZ` at `0x100418782`
- `sqlmin!?StaticInit@InstanceHistoryStoreManager@@SAJXZ` at `0x100418782`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100416b40`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100417bf8`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100417c1a`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100416b40`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100417bf8`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100417c1a`
- `sqlmin!??1CaptureStartupPhaseTelemetry@@QEAA@XZ` at `0x100416a4a`
- `sqlmin!??1CaptureStartupPhaseTelemetry@@QEAA@XZ` at `0x100417c43`
- `sqlmin!??1CaptureStartupPhaseTelemetry@@QEAA@XZ` at `0x100417c65`
- `sqlmin!??1CaptureStartupPhaseTelemetry@@QEAA@XZ` at `0x100416a4a`
- `sqlmin!??1CaptureStartupPhaseTelemetry@@QEAA@XZ` at `0x100417c43`
- `sqlmin!??1CaptureStartupPhaseTelemetry@@QEAA@XZ` at `0x100417c65`
- `sqlmin!??0CaptureStartupPhaseTelemetry@@QEAA@H@Z` at `0x1004169cd`
- `sqlmin!??0CaptureStartupPhaseTelemetry@@QEAA@H@Z` at `0x100417c32`
- `sqlmin!??0CaptureStartupPhaseTelemetry@@QEAA@H@Z` at `0x100417c52`
- `sqlmin!??0CaptureStartupPhaseTelemetry@@QEAA@H@Z` at `0x1004169cd`
- `sqlmin!??0CaptureStartupPhaseTelemetry@@QEAA@H@Z` at `0x100417c32`
- `sqlmin!??0CaptureStartupPhaseTelemetry@@QEAA@H@Z` at `0x100417c52`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100417f0b`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100417ffe`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100418773`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100417f0b`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100417ffe`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100418773`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100417e74`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100417e74`
- `sqlmin!SetMasterDataPath` at `0x100416e26`
- `sqlmin!SetMasterDataPath` at `0x100416e26`
- `sqlmin!GetSqlServerGlobals` at `0x100416d28`
- `sqlmin!GetSqlServerGlobals` at `0x100416d3f`
- `sqlmin!GetSqlServerGlobals` at `0x100416d28`
- `sqlmin!GetSqlServerGlobals` at `0x100416d3f`
- `sqlmin!GetXdbServerGlobals` at `0x100416bc6`
- `sqlmin!GetXdbServerGlobals` at `0x100416bde`
- `sqlmin!GetXdbServerGlobals` at `0x100416bf1`
- `sqlmin!GetXdbServerGlobals` at `0x100416c15`
- `sqlmin!GetXdbServerGlobals` at `0x100416c79`
- `sqlmin!GetXdbServerGlobals` at `0x1004170ee`
- `sqlmin!GetXdbServerGlobals` at `0x1004170fa`
- `sqlmin!GetXdbServerGlobals` at `0x100417107`
- `sqlmin!GetXdbServerGlobals` at `0x100417114`
- `sqlmin!GetXdbServerGlobals` at `0x100417123`
- `sqlmin!GetXdbServerGlobals` at `0x100417138`
- `sqlmin!GetXdbServerGlobals` at `0x100417144`
- `sqlmin!GetXdbServerGlobals` at `0x100417176`
- `sqlmin!GetXdbServerGlobals` at `0x100417259`
- `sqlmin!GetXdbServerGlobals` at `0x100417f1a`
- `sqlmin!GetXdbServerGlobals` at `0x100416bc6`
- `sqlmin!GetXdbServerGlobals` at `0x100416bde`
- `sqlmin!GetXdbServerGlobals` at `0x100416bf1`
- `sqlmin!GetXdbServerGlobals` at `0x100416c15`
- `sqlmin!GetXdbServerGlobals` at `0x100416c79`
- `sqlmin!GetXdbServerGlobals` at `0x1004170ee`
- `sqlmin!GetXdbServerGlobals` at `0x1004170fa`
- `sqlmin!GetXdbServerGlobals` at `0x100417107`
- `sqlmin!GetXdbServerGlobals` at `0x100417114`
- `sqlmin!GetXdbServerGlobals` at `0x100417123`
- `sqlmin!GetXdbServerGlobals` at `0x100417138`
- `sqlmin!GetXdbServerGlobals` at `0x100417144`
- `sqlmin!GetXdbServerGlobals` at `0x100417176`
- `sqlmin!GetXdbServerGlobals` at `0x100417259`
- `sqlmin!GetXdbServerGlobals` at `0x100417f1a`
- `sqlmin!?GetHadrGlobals@@YAPEAUHadrGlobals@@XZ` at `0x10041738d`
- `sqlmin!?GetHadrGlobals@@YAPEAUHadrGlobals@@XZ` at `0x100417396`
- `sqlmin!?GetHadrGlobals@@YAPEAUHadrGlobals@@XZ` at `0x1004173b2`
- `sqlmin!?GetHadrGlobals@@YAPEAUHadrGlobals@@XZ` at `0x100417d13`
- `sqlmin!?GetHadrGlobals@@YAPEAUHadrGlobals@@XZ` at `0x100417d1d`
- `sqlmin!?GetHadrGlobals@@YAPEAUHadrGlobals@@XZ` at `0x100417d39`
- `sqlmin!?GetHadrGlobals@@YAPEAUHadrGlobals@@XZ` at `0x10041738d`
- `sqlmin!?GetHadrGlobals@@YAPEAUHadrGlobals@@XZ` at `0x100417396`
- `sqlmin!?GetHadrGlobals@@YAPEAUHadrGlobals@@XZ` at `0x1004173b2`
- `sqlmin!?GetHadrGlobals@@YAPEAUHadrGlobals@@XZ` at `0x100417d13`
- `sqlmin!?GetHadrGlobals@@YAPEAUHadrGlobals@@XZ` at `0x100417d1d`
- `sqlmin!?GetHadrGlobals@@YAPEAUHadrGlobals@@XZ` at `0x100417d39`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x1004168ca`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100416954`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x1004169fb`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100416af6`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100416c90`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100416dd5`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100416e37`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x1004172bc`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100417629`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100417a4b`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x1004168ca`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100416954`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x1004169fb`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100416af6`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100416c90`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100416dd5`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100416e37`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x1004172bc`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100417629`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100417a4b`
- `sqlmin!?GetNamedObjectSecurityAttributes@StartUp@@SAPEAU_SECURITY_ATTRIBUTES@@XZ` at `0x100417a95`
- `sqlmin!?GetNamedObjectSecurityAttributes@StartUp@@SAPEAU_SECURITY_ATTRIBUTES@@XZ` at `0x100417a95`
- `sqllang!?InitPolarisBackgroundTasks@@YA_NXZ` at `0x100418754`
- `sqllang!?InitPolarisBackgroundTasks@@YA_NXZ` at `0x100418754`
- `sqllang!?VerifyTrust@@YAXXZ` at `0x10041802f`
- `sqllang!?VerifyTrust@@YAXXZ` at `0x10041802f`
- `sqllang!?LogStartupCollation@CErrorReportingManager@@QEAAX_N@Z` at `0x100417d95`
- `sqllang!?LogStartupCollation@CErrorReportingManager@@QEAAX_N@Z` at `0x100417d95`
- `sqllang!?InitSQLServerTime@@YAXXZ` at `0x100416d47`
- `sqllang!?InitSQLServerTime@@YAXXZ` at `0x100416d47`
- `sqllang!?SetDualTimeZoneSqlErrorReportingManager@@YAXXZ` at `0x100416c07`
- `sqllang!?SetDualTimeZoneSqlErrorReportingManager@@YAXXZ` at `0x100416c07`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100417293`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100417f71`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x10041803a`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x10041805e`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100418745`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100417293`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100417f71`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x10041803a`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x10041805e`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100418745`
- `sqllang!?InitEventLog@CErrorReportingManager@@QEAAXXZ` at `0x100416ede`
- `sqllang!?InitEventLog@CErrorReportingManager@@QEAAXXZ` at `0x100416ede`
- `sqllang!?LogStartupMessages@CErrorReportingManager@@QEAAX_N@Z` at `0x1004174fc`
- `sqllang!?LogStartupMessages@CErrorReportingManager@@QEAAX_N@Z` at `0x1004174fc`

## string_xrefs

- `0x100416801`: `__MSSQL_XCOPY_SETUP`
- `0x100417edb`: `sqldk.dll`
- `0x100417ee7`: `sqlmin.dll`
- `0x100417b8d`: `dkdll.dll`
- `0x100416a85`: `SQL.Config`
- `0x100416aa5`: `SQL.Config`
- `0x100416ac5`: `SQL.Config`
- `0x100417723`: `SQL.Config`
- `0x100417741`: `SQL.Config`
- `0x10041775f`: `SQL.Config`
- `0x10041777d`: `SQL.Config`
- `0x1004177d6`: `SQL.Config`
- `0x100416967`: `DCOM CreateThread failure.`
- `0x1004168dd`: `DCOM CreateEvent failure.`
- `0x100416a9e`: `EnableReplicaInfoCacheForAuxiliaryReplica`
- `0x100416a7e`: `EnableInstanceConfigStore`
- `0x100417fda`: `EnableInstanceConfigStore`
- `0x100416b09`: `Instance Config Store Manager failure.`
- `0x100416abe`: `PersistTempdbFileLayout`
- `0x100417fa2`: `PersistTempdbFileLayout`
- `0x100416ca3`: `String Copy Error (TimeZoneName)`
- `0x100416e4a`: `String copy failure (master.mdf)`
- `0x1004173d8`: `Enabling HADR for this XCopy instance. May not work properly if prerequisites are not met.\n`
- `0x100417912`: `SqlServer is starting with Affinity Agnostic configuration`
- `0x100417b43`: `BlobAccess_FileSystemInit`
- `0x100417893`: `SqlServer is starting with non-static configuration (enumerate all cores on the node)`
- `0x100417c0e`: `InstanceConfigStore initial startup get completed with code: %d.\n`
- `0x100417fba`: `Failed to subscribe Instance Config Store on a feature switch change.\n`
- `0x100417ff2`: `Failed to subscribe Instance Config Store on a feature switch change.\n`
- `0x10041878a`: `Instance History Store Manager initialization completed with code: %d.\n`
- `0x1004175b3`: `Failed to read time zone info for time zone id '%ls' from registry.`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=12
void sqlservr_main(void)
{
  unsigned int v0; // ebx
  int v1; // eax
  __int64 *v2; // rsi
  const WCHAR *v3; // rdx
  HANDLE EventW; // rdi
  signed int LastError; // eax
  int v6; // ebx
  struct __crt_locale_pointers *DefaultLocale; // rax
  int v8; // eax
  char *v9; // rcx
  HANDLE Thread; // rax
  signed int v11; // eax
  int v12; // ebx
  struct __crt_locale_pointers *v13; // rax
  signed int inited; // eax
  signed int v15; // ebx
  struct __crt_locale_pointers *v16; // rax
  int v17; // eax
  char *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rcx
  char IsFeatureSwitchOn; // bl
  char v23; // di
  char v24; // al
  signed int v25; // eax
  signed int v26; // ebx
  struct __crt_locale_pointers *v27; // rax
  int v28; // eax
  char *v29; // rcx
  InstanceConfigStoreManager *InstanceConfigStoreManager; // rax
  unsigned int v31; // ebx
  unsigned int v32; // ebx
  signed int v33; // r15d
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r13
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 XdbServerGlobals; // rax
  signed int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rbx
  _WORD *v45; // rdx
  __int64 v46; // r8
  __int64 v47; // rcx
  __int16 v48; // ax
  _WORD *v49; // rax
  unsigned int v50; // edi
  struct __crt_locale_pointers *v51; // rax
  int v52; // eax
  char *v53; // rcx
  const wchar_t *v54; // rcx
  __int64 v55; // rbx
  char v56; // bl
  signed int v57; // eax
  signed int v58; // ebx
  struct __crt_locale_pointers *v59; // rax
  int v60; // eax
  char *v61; // rcx
  signed int v62; // eax
  signed int v63; // ebx
  struct __crt_locale_pointers *v64; // rax
  int v65; // eax
  char *v66; // rcx
  RESOURCE *v67; // rbx
  CErrorReportingManager *ErrorReportingManager; // rax
  RESOURCE *v69; // rax
  struct IErrorReportingManager *v70; // rax
  unsigned int v71; // eax
  __int64 v72; // rcx
  struct IErrorReportingManager *v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rcx
  bool v76; // bl
  __int64 v77; // rdx
  __int64 v78; // rcx
  __int64 v79; // rdx
  __int64 v80; // rcx
  __int64 v81; // rdx
  __int64 v82; // rcx
  bool v83; // bl
  __int64 v84; // rdx
  wchar_t *v85; // rcx
  int v86; // ebx
  int v87; // ecx
  DWORD v88; // r14d
  int v89; // edi
  RESOURCE *v90; // rax
  int v91; // eax
  signed int v92; // eax
  signed int v93; // ebx
  struct __crt_locale_pointers *v94; // rax
  int v95; // r12d
  __int64 v96; // rax
  int v97; // ebx
  struct IErrorReportingManager *v98; // rax
  __int64 v99; // r9
  struct IServerConfiguration *v100; // rdx
  __int64 v101; // r8
  struct CSessionTraceFlags *v102; // rcx
  int v103; // ecx
  struct IErrorReportingManager *v104; // rax
  CErrorReportingManager *v105; // rax
  wchar_t *v106; // rcx
  struct __crt_locale_pointers *v107; // rax
  int v108; // eax
  char *v109; // rcx
  int v110; // edx
  WORD ActiveProcessorGroupCount; // ax
  int v112; // r15d
  char v113; // al
  char v114; // al
  bool v115; // di
  GroupAffinity *LastGroupSet; // rax
  unsigned __int16 Group; // bx
  GroupAffinity *FirstGroupSet; // rax
  const wchar_t *v119; // rdx
  __int64 v120; // rax
  WCHAR *v121; // rcx
  signed __int64 v122; // rdx
  WCHAR v123; // ax
  WCHAR *v124; // rax
  signed int v125; // ebx
  __int64 v126; // rbx
  struct __crt_locale_pointers *v127; // rax
  struct __crt_locale_pointers *v128; // rax
  int v129; // eax
  char *v130; // rcx
  struct _SECURITY_ATTRIBUTES *NamedObjectSecurityAttributes; // rax
  HANDLE FileMappingW; // rbx
  _BYTE *v133; // rax
  HMODULE LibraryW; // rax
  DWORD v135; // eax
  InstanceConfigStoreManager *v136; // rax
  unsigned int PropertyBagComplete; // eax
  InstanceConfigStoreManager *v138; // rax
  int v139; // ebx
  RESOURCE *v140; // rcx
  struct IErrorReportingManager *v141; // rax
  __int64 v142; // r9
  CErrorReportingManager *v143; // rax
  char *v144; // rax
  unsigned __int16 v145; // di
  unsigned __int16 i; // bx
  __int64 NodeAffinity; // rax
  char *v148; // rcx
  __int64 v149; // rcx
  unsigned int v150; // ebx
  __int64 v151; // rdx
  __int64 v152; // rcx
  __int64 v153; // rcx
  __int64 v154; // rbx
  __int64 *v155; // rdi
  volatile signed __int64 *v156; // r12
  LARGE_INTEGER v157; // rbx
  signed __int64 UniqueThread_low; // r13
  __int64 v159; // r15
  __int64 v160; // r8
  LARGE_INTEGER v161; // rax
  LONGLONG v162; // rcx
  _QWORD *v163; // rcx
  __int64 v164; // rax
  volatile signed __int64 *v165; // rbx
  int v166; // r8d
  __int64 v167; // r8
  __int64 v168; // rax
  __int64 *v169; // rsi
  __int64 v170; // rbx
  SOS_Node *v171; // rcx
  __int64 v172; // r15
  __int64 *v173; // rcx
  __int64 *v174; // rcx
  __int64 v175; // rbx
  __int64 *v176; // r14
  __int64 v177; // rdi
  LARGE_INTEGER v178; // rbx
  signed __int64 v179; // r13
  __int64 v180; // r15
  __int64 v181; // r8
  __int64 v182; // rcx
  LARGE_INTEGER v183; // rax
  LONGLONG v184; // rcx
  __int64 *v185; // rcx
  unsigned __int64 v186; // rax
  SOS_ObjectStore *v187; // rcx
  __int64 PoolIdForObject; // r10
  __int64 v189; // rax
  _QWORD *v190; // r8
  __int64 v191; // rcx
  int v192; // r8d
  int v193; // r8d
  __int64 *v194; // rcx
  bool v195; // zf
  __int64 *v196; // rdi
  __int64 v197; // rbx
  __int64 v198; // rcx
  unsigned int v199; // eax
  LPDWORD lpThreadId; // [rsp+28h] [rbp-D8h]
  char v201; // [rsp+30h] [rbp-D0h] BYREF
  char v202; // [rsp+31h] [rbp-CFh] BYREF
  char v203; // [rsp+32h] [rbp-CEh]
  char v204; // [rsp+33h] [rbp-CDh]
  char v205; // [rsp+34h] [rbp-CCh]
  __int64 *v206; // [rsp+38h] [rbp-C8h]
  size_t MaxCount; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v208; // [rsp+48h] [rbp-B8h] BYREF
  int v209; // [rsp+50h] [rbp-B0h] BYREF
  DWORD flOldProtect; // [rsp+54h] [rbp-ACh] BYREF
  void *v211; // [rsp+58h] [rbp-A8h] BYREF
  volatile signed __int32 *v212; // [rsp+60h] [rbp-A0h] BYREF
  volatile signed __int64 *v213; // [rsp+68h] [rbp-98h]
  int v214; // [rsp+70h] [rbp-90h]
  HKEY v215; // [rsp+78h] [rbp-88h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp-80h] BYREF
  LARGE_INTEGER v217; // [rsp+88h] [rbp-78h] BYREF
  LARGE_INTEGER v218; // [rsp+90h] [rbp-70h] BYREF
  LARGE_INTEGER v219; // [rsp+98h] [rbp-68h] BYREF
  int v220; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v221; // [rsp+A8h] [rbp-58h]
  __int64 v222; // [rsp+B0h] [rbp-50h]
  __int64 v223; // [rsp+B8h] [rbp-48h]
  __int64 v224; // [rsp+C0h] [rbp-40h]
  __int64 v225; // [rsp+C8h] [rbp-38h]
  _QWORD v226[10]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v227[16]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v228[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v229[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v230[32]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v231[16]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v232[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v233[128]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v234[128]; // [rsp+230h] [rbp+130h] BYREF
  wchar_t Source[64]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR Name[264]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v237[528]; // [rsp+540h] [rbp+440h] BYREF
  _BYTE v238[528]; // [rsp+750h] [rbp+650h] BYREF
  wchar_t v239[360]; // [rsp+960h] [rbp+860h] BYREF
  char v240[512]; // [rsp+C30h] [rbp+B30h] BYREF
  char v241[512]; // [rsp+E30h] [rbp+D30h] BYREF
  char v242[512]; // [rsp+1030h] [rbp+F30h] BYREF
  char v243[512]; // [rsp+1230h] [rbp+1130h] BYREF
  char v244[512]; // [rsp+1430h] [rbp+1330h] BYREF
  char v245[512]; // [rsp+1630h] [rbp+1530h] BYREF
  char v246[512]; // [rsp+1830h] [rbp+1730h] BYREF
  char v247[512]; // [rsp+1A30h] [rbp+1930h] BYREF
  char v248[512]; // [rsp+1C30h] [rbp+1B30h] BYREF
  char v249[512]; // [rsp+1E30h] [rbp+1D30h] BYREF
  wchar_t v250[2048]; // [rsp+2030h] [rbp+1F30h] BYREF
  wchar_t v251[2048]; // [rsp+3030h] [rbp+2F30h] BYREF
  wchar_t Buffer[2048]; // [rsp+4030h] [rbp+3F30h] BYREF
  wchar_t v253[2048]; // [rsp+5030h] [rbp+4F30h] BYREF
  wchar_t v254[2048]; // [rsp+6030h] [rbp+5F30h] BYREF

  v225 = -2;
  v0 = DkParametersProcessor::Execute(&qword_1004A1720, 256);
  if ( v0 )
  {
    InitializeErrorReportingForStartupFailure();
    LogInvalidParameterInCommandLine(v0, &qword_1004A1720);
  }
  v1 = IsXCopySetupInstance();
  v2 = 0;
  v3 = 0;
  if ( v1 )
    v3 = L"True";
  SetEnvironmentVariableW(L"__MSSQL_XCOPY_SETUP", v3);
  if ( *((_DWORD *)qword_10049F360 + 3626) && *(char *)(qword_10049F340 + 1107) >= 0 )
    RgClient_InitETWTrace(0);
  if ( (unsigned int)SOS_OS::RegisterProcess(clientProcessConfig, 1) )
  {
    scierrlog(0x42F2u, L"RegisterWithSOS");
    SQLExit(46);
  }
  if ( (unsigned int)SOS_OS::PreBoot() )
  {
    LogStartupFailure(0x42AFu);
    SOS_OS::KillProcess(0x410u);
    SQLExit(47);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
    {
      _mm_lfence();
      SetWin32ExitCode(v6);
      DefaultLocale = GetDefaultLocale();
      v8 = StringCchPrintf_lA(v240, 0x200u, "%hs (HRESULT 0x%x)", DefaultLocale, "DCOM CreateEvent failure.", v6);
      v9 = "DCOM CreateEvent failure.";
      if ( v8 >= 0 )
        v9 = v240;
      FailAndExit(v9);
    }
  }
  Thread = CreateThread(0, 0, DCOMInitThread, EventW, 0, 0);
  if ( Thread )
  {
    CloseHandle(Thread);
  }
  else
  {
    v11 = GetLastError();
    v12 = v11;
    if ( v11 > 0 )
      v12 = (unsigned __int16)v11 | 0x80070000;
    if ( v12 < 0 )
    {
      _mm_lfence();
      SetWin32ExitCode(v12);
      v13 = GetDefaultLocale();
      LODWORD(lpThreadId) = v12;
      if ( (int)StringCchPrintf_lA(v241, 0x200u, "%hs (HRESULT 0x%x)", v13, "DCOM CreateThread failure.", lpThreadId) >= 0 )
        FailAndExit(v241);
      else
        FailAndExit("DCOM CreateThread failure.");
    }
  }
  WaitForSingleObject(EventW, 0xFFFFFFFF);
  CloseHandle(EventW);
  CaptureStartupPhaseTelemetry::CaptureStartupPhaseTelemetry((CaptureStartupPhaseTelemetry *)v228, 0);
  inited = InitFabric(v250, 0x800u, v251, 0x800u);
  v15 = inited;
  if ( inited < 0 )
  {
    _mm_lfence();
    SetWin32ExitCode(inited);
    v16 = GetDefaultLocale();
    LODWORD(lpThreadId) = v15;
    v17 = StringCchPrintf_lA(v242, 0x200u, "%hs (HRESULT 0x%x)", v16, "XDB Host registration failure.", lpThreadId);
    v18 = "XDB Host registration failure.";
    if ( v17 >= 0 )
      v18 = v242;
    FailAndExit(v18);
  }
  CaptureStartupPhaseTelemetry::~CaptureStartupPhaseTelemetry((CaptureStartupPhaseTelemetry *)v228);
  v202 = 0;
  v204 = 0;
  v203 = 0;
  LOBYTE(v21) = 0;
  v205 = 0;
  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    if ( (IsFeatureSwitchOn = HostReg_IsFeatureSwitchOn(L"SQL.Config", L"EnableInstanceConfigStore", &v202),
          v204 = IsFeatureSwitchOn,
          v23 = HostReg_IsFeatureSwitchOn(L"SQL.Config", L"EnableReplicaInfoCacheForAuxiliaryReplica", &v202),
          v203 = v23,
          v24 = HostReg_IsFeatureSwitchOn(L"SQL.Config", L"PersistTempdbFileLayout", &v202),
          v205 = v24,
          !v23)
      && IsFeatureSwitchOn
      || v24 )
    {
      v25 = InstanceConfigStoreManager::StaticInit(0);
      v26 = v25;
      if ( v25 < 0 )
      {
        _mm_lfence();
        SetWin32ExitCode(v25);
        v27 = GetDefaultLocale();
        LODWORD(lpThreadId) = v26;
        v28 = StringCchPrintf_lA(
                v243,
                0x200u,
                "%hs (HRESULT 0x%x)",
                v27,
                "Instance Config Store Manager failure.",
                lpThreadId);
        v29 = "Instance Config Store Manager failure.";
        if ( v28 >= 0 )
          v29 = v243;
        FailAndExit(v29);
      }
      InstanceConfigStoreManager = (InstanceConfigStoreManager *)InstanceConfigStoreManager::GetInstanceConfigStoreManager();
      InstanceConfigStoreManager::GetPropertyBagStart(InstanceConfigStoreManager);
    }
  }
  if ( v250[0] )
  {
    LOBYTE(v20) = 1;
    v31 = DkParametersProcessor::ProcessBuffer(&qword_1004A1720, v250, v20);
    if ( v31 )
    {
      InitializeErrorReportingForStartupFailure();
      LogInvalidParameterInCommandLine(v31, &qword_1004A1720);
    }
  }
  if ( v251[0] )
  {
    LOBYTE(v20) = 1;
    v32 = DkParametersProcessor::ProcessBuffer(&qword_1004A17A0, v251, v20);
    if ( v32 )
    {
      InitializeErrorReportingForStartupFailure();
      LogInvalidParameterInCommandLine(v32, &qword_1004A17A0);
    }
  }
  v33 = 0;
  v36 = 261;
  if ( *(_DWORD *)(GetXdbServerGlobals(v21, v19) + 11976) && *(_BYTE *)(GetXdbServerGlobals(v35, v34) + 22940) )
  {
    XdbServerGlobals = GetXdbServerGlobals(v38, v37);
    v40 = InitCLDetours((const wchar_t *)(XdbServerGlobals + 22942));
    if ( v40 )
    {
      v33 = v40;
      v43 = GetXdbServerGlobals(v42, v41);
      v44 = 261;
      v45 = v238;
      v46 = v43 + 22942 - (_QWORD)v238;
      do
      {
        v47 = v44 + 2147483385;
        if ( v44 == -2147483385 )
          break;
        v48 = *(_WORD *)((char *)v45 + v46);
        if ( !v48 )
          break;
        *v45++ = v48;
        --v44;
      }
      while ( v44 );
      v49 = v45 - 1;
      if ( v44 )
        v49 = v45;
      *v49 = 0;
      v50 = -2147024774;
      if ( v44 )
        v50 = 0;
      *(_BYTE *)(GetXdbServerGlobals(v47, v45) + 22940) = 0;
      if ( !v44 )
      {
        _mm_lfence();
        SetWin32ExitCode(v50);
        v51 = GetDefaultLocale();
        LODWORD(lpThreadId) = v50;
        v52 = StringCchPrintf_lA(
                v244,
                0x200u,
                "%hs (HRESULT 0x%x)",
                v51,
                "String Copy Error (TimeZoneName)",
                lpThreadId);
        v53 = "String Copy Error (TimeZoneName)";
        if ( v52 >= 0 )
          v53 = v244;
        FailAndExit(v53);
      }
    }
    else
    {
      SetDualTimeZoneSqlErrorReportingManager();
    }
  }
  SetSystemTimeZoneDisplayName();
  v54 = (const wchar_t *)((char *)qword_10049F360 + 43256);
  if ( *((_DWORD *)qword_10049F360 + 3636) )
  {
    BuildInstanceNameInit();
  }
  else if ( ParentInstanceName )
  {
    UserInstanceNameInit(v54, &ParentInstanceName);
  }
  else
  {
    SQLInstanceNameInit(v54);
  }
  v55 = *((_QWORD *)qword_10049F360 + 1466);
  *(_QWORD *)(GetSqlServerGlobals() + 8) = v55;
  LODWORD(v55) = *((_DWORD *)qword_10049F360 + 2934);
  *(_DWORD *)GetSqlServerGlobals() = v55;
  InitSQLServerTime();
  InitializeLocale();
  v56 = _statusfp();
  if ( (v56 & 0x1C) != 0 )
  {
    _clearfp();
    if ( (v56 & 0x10) != 0 )
      _fpreset();
  }
  _controlfp(0x9001Fu, 0x8031Fu);
  v208 = 0;
  if ( OsInfo::IsLinux(SOS_OS_OsInfo) )
  {
    LOBYTE(v208) = 1;
    HIDWORD(v208) = 2;
    if ( (*(_BYTE *)(qword_10049F340 + 638) & 0x10) == 0 )
      BYTE1(v208) = 1;
  }
  else
  {
    HIDWORD(v208) = 1;
  }
  v57 = SvlSystemInitialize(&v208);
  v58 = v57;
  if ( v57 < 0 )
  {
    _mm_lfence();
    SetWin32ExitCode(v57);
    v59 = GetDefaultLocale();
    LODWORD(lpThreadId) = v58;
    v60 = StringCchPrintf_lA(v245, 0x200u, "%hs (HRESULT 0x%x)", v59, "Storage host initialization.", lpThreadId);
    v61 = "Storage host initialization.";
    if ( v60 >= 0 )
      v61 = v245;
    FailAndExit(v61);
  }
  v62 = SetMasterDataPath(L"master.mdf");
  v63 = v62;
  if ( v62 < 0 )
  {
    _mm_lfence();
    SetWin32ExitCode(v62);
    v64 = GetDefaultLocale();
    LODWORD(lpThreadId) = v63;
    v65 = StringCchPrintf_lA(v249, 0x200u, "%hs (HRESULT 0x%x)", v64, "String copy failure (master.mdf)", lpThreadId);
    v66 = "String copy failure (master.mdf)";
    if ( v65 >= 0 )
      v66 = v249;
    FailAndExit(v66);
  }
  CSqlTypeSystemHost::PreInitializeTypeSystem();
  CESRuntimeIntializer::PreInitializeRunTime();
  RESOURCE::SetIsBdcInstance(qword_10049F360);
  v67 = qword_10049F360;
  if ( GetEnvironmentVariableW(L"ARC_POD_TYPE", 0, 0) > 1 )
    *((_BYTE *)v67 + 48776) = 1;
  SOS_OS_LoadLibraryRoutine = (HINSTANCE (*)(const wchar_t *, int, const wchar_t *, int))ServerLoadLibraryCallback;
  StartUp::SetupNamedObjectSecurity();
  ErrorReportingManager = GetErrorReportingManager();
  CErrorReportingManager::InitEventLog(ErrorReportingManager);
  if ( OsInfo::IsXPlatInstance(SOS_OS_OsInfo) )
    *((_DWORD *)qword_10049F360 + 3624) = 1;
  if ( !OsInfo::IsLinux(SOS_OS_OsInfo) )
  {
    v69 = qword_10049F360;
    if ( !*((_DWORD *)qword_10049F360 + 3624) )
      goto LABEL_103;
    if ( *((_DWORD *)qword_10049F360 + 3626) )
    {
      if ( (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) == 2
        || (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) == 3 )
      {
        goto LABEL_103;
      }
      v69 = qword_10049F360;
    }
    if ( !*((_DWORD *)v69 + 3625)
      && (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) != 2
      && (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) != 3 )
    {
      goto LABEL_103;
    }
  }
  v70 = GetErrorReportingManager();
  (*(void (__fastcall **)(struct IErrorReportingManager *))(*(_QWORD *)v70 + 208LL))(v70);
  LODWORD(MaxCount) = 64;
  SQLLicense::SQLLicense((SQLLicense *)v226);
  v226[0] = &SQLLicenseSupportXCopySetup::`vftable';
  SQLLicense::SetIsEdgeInstance((SQLLicense *)v226, 0);
  SQLLicense::SetIsMIAAInstance((SQLLicense *)v226, 0);
  SQLLicense::Initialize((SQLLicense *)v226, SOS_OS_LoadLibraryRoutine);
  if ( !(unsigned int)IniRegOpenKeyExW(
                        -2147483646,
                        (int)L"SOFTWARE\\Microsoft\\Microsoft SQL Server\\MSSQL\\MSSQLServer\\Licensing",
                        0,
                        1,
                        &v215)
    && !(unsigned int)IniRegQueryValueExW((int)v215, (int)L"PID", 0, 0, (LPBYTE)Source, (LPDWORD)&MaxCount) )
  {
    v71 = wcsnlen(Source, (unsigned int)MaxCount);
    if ( SetLicensingInformation(Source, v71, (struct SQLLicenseSupportXCopySetup *)v226) )
      goto LABEL_103;
    v72 = 314;
    goto LABEL_102;
  }
  if ( (*((_DWORD *)qword_10049F360 + 12127) & 0x800) != 0
    && !SetLicensingInformation(
          (const wchar_t *)qword_10049F360 + 21360,
          *((_DWORD *)qword_10049F360 + 10811),
          (struct SQLLicenseSupportXCopySetup *)v226) )
  {
    v72 = 315;
LABEL_102:
    SQLExit(v72);
  }
LABEL_103:
  read_reg_params();
  v73 = GetErrorReportingManager();
  (*(void (__fastcall **)(struct IErrorReportingManager *))(*(_QWORD *)v73 + 208LL))(v73);
  ProcessCmdLineAndRegistryParameters();
  if ( !*((_DWORD *)qword_10049F360 + 3626) )
  {
    v76 = (*(_BYTE *)(qword_10049F340 + 1512) & 0x10) != 0;
    *(_WORD *)(GetXdbServerGlobals(v75, v74) + 12004) = v76;
    *(_BYTE *)(GetXdbServerGlobals(v78, v77) + 12006) = 0;
    v83 = *(_BYTE *)(GetXdbServerGlobals(v80, v79) + 12005) || *(_BYTE *)(GetXdbServerGlobals(v82, v81) + 12006);
    *(_BYTE *)(GetXdbServerGlobals(v82, v81) + 12007) = v83;
  }
  if ( *(_BYTE *)(GetXdbServerGlobals(v75, v74) + 12004) )
    AzureDWVersion = getAzureDWVersion();
  v85 = (wchar_t *)qword_10049F340;
  if ( (*(_BYTE *)(qword_10049F340 + 1196) & 1) != 0 )
  {
    v86 = 0;
    v87 = *(_DWORD *)(GetXdbServerGlobals(qword_10049F340, v84) + 12000);
    v88 = 5000;
    if ( !v87 )
      v88 = 10000;
    v89 = 3;
    if ( !v87 )
      v89 = 30;
    for ( ; !IsDebuggerPresent(); ++v86 )
    {
      if ( v86 >= v89 )
        break;
      Sleep(v88);
    }
    v85 = (wchar_t *)qword_10049F340;
  }
  v90 = qword_10049F360;
  if ( !*((_DWORD *)qword_10049F360 + 3626) && *((_DWORD *)qword_10049F360 + 3624) )
  {
    if ( (*((_BYTE *)v85 + 1731) & 4) == 0 )
    {
      v85 = (wchar_t *)SystemThread_TlsIndex;
      v84 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      if ( !*(_QWORD *)v84 )
        goto LABEL_129;
      v85 = **(wchar_t ***)(*(_QWORD *)v84 + 56LL);
      if ( !v85 || !CSessionTraceFlags::CheckSessionTraceInternal((struct CSessionTraceFlags *)v85, 0x361Au) )
        goto LABEL_129;
      v90 = qword_10049F360;
    }
    if ( *((_DWORD *)v90 + 2935) == 1804890536 )
    {
      v85 = L"Business Critical Edition (64-bit)";
      wszBundle = L"Business Critical Edition (64-bit)";
      *((_DWORD *)v90 + 2935) = 1020889822;
    }
  }
LABEL_129:
  if ( *(_DWORD *)(GetXdbServerGlobals(v85, v84) + 11976) )
  {
    v91 = *((_DWORD *)qword_10049F360 + 12127);
    if ( (v91 & 4) != 0 )
      *((_DWORD *)qword_10049F360 + 12127) = v91 & 0xFFFFFFFE;
  }
  if ( OsInfo::IsXPlatInstance(SOS_OS_OsInfo) )
  {
    CFeatureSwitchesLangSvc::GetCurrentInstance();
    v92 = BootstrapSystemDataDirectories((*((_DWORD *)qword_10049F360 + 12127) & 0x400) != 0);
    v93 = v92;
    if ( v92 < 0 )
    {
      _mm_lfence();
      SetWin32ExitCode(v92);
      v94 = GetDefaultLocale();
      LODWORD(lpThreadId) = v93;
      if ( (int)StringCchPrintf_lA(
                  v246,
                  0x200u,
                  "%hs (HRESULT 0x%x)",
                  v94,
                  "BootstrapSystemDataDirectories() failure",
                  lpThreadId) >= 0 )
        FailAndExit(v246);
      else
        FailAndExit("BootstrapSystemDataDirectories() failure");
    }
  }
  else if ( (unsigned int)IsXCopySetupInstance() )
  {
    CheckEULA();
    *((_DWORD *)qword_10049F360 + 3632) = 1;
  }
  v95 = 4;
  v96 = qword_10049F340;
  if ( *((_DWORD *)qword_10049F360 + 3624) && (*(_BYTE *)(qword_10049F340 + 1198) & 1) != 0
    || *((_DWORD *)qword_10049F360 + 3628) )
  {
    if ( (*(_BYTE *)(qword_10049F340 + 1197) & 0x20) != 0 )
      v97 = 4;
    else
      v97 = ((*(_BYTE *)(qword_10049F340 + 1198) & 2) != 0) | 2;
    *((_DWORD *)GetHadrGlobals() + 2) = v97;
    *(_DWORD *)GetHadrGlobals() = 1;
    if ( (*(_BYTE *)(qword_10049F340 + 1199) & 4) != 0 )
      *((_WORD *)GetHadrGlobals() + 2) = 8088;
    v98 = GetErrorReportingManager();
    LOBYTE(v99) = 1;
    (*(void (__fastcall **)(struct IErrorReportingManager *, const wchar_t *, __int64, __int64, int))(*(_QWORD *)v98 + 168LL))(
      v98,
      L"Enabling HADR for this XCopy instance. May not work properly if prerequisites are not met.\n",
      91,
      v99,
      -1);
    v96 = qword_10049F340;
  }
  if ( (*(_BYTE *)(v96 + 1207) & 2) != 0 )
  {
    if ( !InitFunctions() )
    {
      scierrlog(0x42F2u, L"SQL Azure Functions");
      SQLExit(48);
    }
    v96 = qword_10049F340;
  }
  if ( !*((_DWORD *)qword_10049F360 + 3626) )
  {
    v100 = s_pServerConf;
    if ( *((_DWORD *)s_pServerConf + 2) == 2 )
    {
      if ( (*(_BYTE *)(v96 + 1250) & 1) == 0 )
      {
        v101 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( !*(_QWORD *)v101 )
          goto LABEL_162;
        v102 = **(struct CSessionTraceFlags ***)(*(_QWORD *)v101 + 56LL);
        if ( !v102 || !CSessionTraceFlags::CheckSessionTraceInternal(v102, 0x2710u) )
          goto LABEL_162;
        v100 = s_pServerConf;
      }
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v100 + 512LL))(*(_QWORD *)v100) == 9507
        || *((_DWORD *)qword_10049F360 + 3624) )
      {
        v103 = 1;
LABEL_163:
        *((_DWORD *)qword_10049F360 + 3635) = v103;
        goto LABEL_164;
      }
    }
LABEL_162:
    v103 = 0;
    goto LABEL_163;
  }
LABEL_164:
  FClusMgr::RegisterSqlClusterInstance();
  v104 = GetErrorReportingManager();
  (*(void (__fastcall **)(struct IErrorReportingManager *, __int64))(*(_QWORD *)v104 + 232LL))(v104, 1);
  v105 = GetErrorReportingManager();
  CErrorReportingManager::LogStartupMessages(v105, 0);
  LogStartupParameters();
  if ( !v33 )
    goto LABEL_178;
  if ( (unsigned __int16)v33 == 2 )
  {
    StringCchPrintfW(v239, 0x168u, L"Failed to read time zone info for time zone id '%ls' from registry.", v238);
    scierrlog(0xA3CDu, v239);
    if ( (int)StringCchPrintfW(
                v254,
                0x800u,
                L"Error: %d. Failed to initalize Managed Instance Local Time. %ls",
                41933,
                v239) < 0 )
      goto LABEL_174;
    v106 = v254;
  }
  else if ( (unsigned __int16)v33 == 6 )
  {
    scierrlog(0xA3CDu, L"Failed to attach detours hooks.");
    if ( (int)StringCchPrintfW(
                v253,
                0x800u,
                L"Error: %d. Failed to initalize Managed Instance Local Time. %ls",
                41933,
                L"Failed to attach detours hooks.") < 0 )
      goto LABEL_174;
    v106 = v253;
  }
  else
  {
    scierrlog(0xA3CDu, L"Unexpected failure.");
    if ( (int)StringCchPrintfW(
                Buffer,
                0x800u,
                L"Error: %d. Failed to initalize Managed Instance Local Time. %ls",
                41933,
                L"Unexpected failure.") < 0 )
      goto LABEL_174;
    v106 = Buffer;
  }
  RgClient_WriteETWTrace(v106, 4, 0);
LABEL_174:
  if ( v33 < 0 )
  {
    _mm_lfence();
    SetWin32ExitCode(v33);
    v107 = GetDefaultLocale();
    LODWORD(lpThreadId) = v33;
    v108 = StringCchPrintf_lA(
             v247,
             0x200u,
             "%hs (HRESULT 0x%x)",
             v107,
             "Failed to initalize local time for Managed Instance",
             lpThreadId);
    v109 = "Failed to initalize local time for Managed Instance";
    if ( v108 >= 0 )
      v109 = v247;
    FailAndExit(v109);
  }
LABEL_178:
  initsignal();
  v110 = days_till_expiration;
  if ( days_till_expiration == -256 )
  {
    scierrlog(0x429Bu);
    SQLExit(298, 17051, 1066);
    v110 = days_till_expiration;
  }
  if ( v110 < 11 && v110 )
    scierrlog(0x42A0u);
  RESOURCE::InitControl(qword_10049F360);
  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    SOS_OS::GetCPUCorePercentCap();
    ActiveProcessorGroupCount = GetActiveProcessorGroupCount();
    v112 = ActiveProcessorGroupCount;
    if ( !ActiveProcessorGroupCount )
    {
      LogSystemMetadataNotSentToClient(L"%ls", L"Failed to check processor group count of system");
      SQLExit((unsigned int)(v112 + 49));
    }
    v201 = 0;
    HostReg_IsFeatureSwitchOn(L"SQL.Config", L"EnableDynamicAffinity", &v201);
    v201 = 0;
    HostReg_IsFeatureSwitchOn(L"SQL.Config", L"DisableMemNumaLocalityCheck", &v201);
    v201 = 0;
    HostReg_IsFeatureSwitchOn(L"SQL.Config", L"EnableSoftAffinityMode", &v201);
    v201 = 0;
    v113 = HostReg_IsFeatureSwitchOn(L"SQL.Config", L"EnableDetourMemObj", &v201);
    if ( v201 && v113 && !(unsigned __int8)CGlobalTraceFlags::TurnOn(8108, 1) )
    {
      LogSystemMetadataNotSentToClient(L"Failed to setup trace flag %d to enable detour mem obj\n", 8108);
      SQLExit(301);
    }
    v201 = 0;
    v114 = HostReg_IsFeatureSwitchOn(L"SQL.Config", L"DeferredSchedulerAllocation", &v201);
    v115 = v201 && v114;
    SystemAffinity::SystemAffinity((SystemAffinity *)v233);
    SOS_OS::GetOsProcessAffinity((struct SystemAffinity *)v233);
    if ( SystemAffinity::IsEmpty((SystemAffinity *)v233)
      || (LastGroupSet = (GroupAffinity *)SystemAffinity::GetLastGroupSet(v233, v232),
          Group = GroupAffinity::GetGroup(LastGroupSet),
          FirstGroupSet = (GroupAffinity *)SystemAffinity::GetFirstGroupSet(v233, v231),
          GroupAffinity::GetGroup(FirstGroupSet) == Group) )
    {
      if ( !(unsigned __int8)CGlobalTraceFlags::TurnOn(8017, 1) )
      {
        LogSystemMetadataNotSentToClient(L"Failed to setup trace flag %d to force static affinity\n", 8017);
        SQLExit(51);
      }
      if ( v112 == 1 && !(unsigned __int8)CGlobalTraceFlags::TurnOn(8015, 1) )
      {
        LogSystemMetadataNotSentToClient(L"Failed to setup trace flag %d to disable numa", 8015);
        SQLExit(52);
      }
      SOS_PublicGlobals::sm_osOptions |= 0x40u;
      v119 = L"SqlServer is starting with Affinity Agnostic configuration";
    }
    else
    {
      if ( !(unsigned __int8)CGlobalTraceFlags::TurnOn(8073, 1) )
      {
        LogSystemMetadataNotSentToClient(L"Failed to setup trace flag %d to allow affinity to be changed\n", 8073);
        SQLExit(53);
      }
      v119 = L"SqlServer is starting with non-static configuration (enumerate all cores on the node)";
    }
    LogSystemMetadataNotSentToClient(L"%ls", v119);
    if ( !(unsigned __int8)CGlobalTraceFlags::TurnOn(8086, 1) )
    {
      LogSystemMetadataNotSentToClient(L"Failed to setup trace flag %d to disable numa", 8086);
      SQLExit(54);
    }
    if ( v115 )
      SOS_PublicGlobals::sm_osOptions |= 0x100u;
  }
  if ( *((_DWORD *)qword_10049F360 + 10544) )
  {
    if ( *((_DWORD *)qword_10049F360 + 3636)
      || (v120 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf),
          !(unsigned int)IsDefaultInstanceName(v120)) )
    {
      v126 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
      v127 = GetDefaultLocale();
      v125 = StringCchPrintf_lW(Name, 0x105u, L"%ls$%ls", v127, L"SQL60_RUNNING", v126);
    }
    else
    {
      v121 = Name;
      v122 = (char *)L"SQL60_RUNNING" - (char *)Name;
      do
      {
        if ( v36 == -2147483385 )
          break;
        v123 = *(WCHAR *)((char *)v121 + v122);
        if ( !v123 )
          break;
        *v121++ = v123;
        --v36;
      }
      while ( v36 );
      v124 = v121 - 1;
      if ( v36 )
        v124 = v121;
      *v124 = 0;
      v125 = -2147024774;
      if ( v36 )
        v125 = 0;
    }
    if ( v125 < 0 )
    {
      _mm_lfence();
      SetWin32ExitCode(v125);
      v128 = GetDefaultLocale();
      LODWORD(lpThreadId) = v125;
      v129 = StringCchPrintf_lA(
               v248,
               0x200u,
               "%hs (HRESULT 0x%x)",
               v128,
               "String operation failure (status block name)",
               lpThreadId);
      v130 = "String operation failure (status block name)";
      if ( v129 >= 0 )
        v130 = v248;
      FailAndExit(v130);
    }
    NamedObjectSecurityAttributes = (struct _SECURITY_ATTRIBUTES *)StartUp::GetNamedObjectSecurityAttributes(v121, v122);
    FileMappingW = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, NamedObjectSecurityAttributes, 4u, 0, 4u, Name);
    if ( FileMappingW )
    {
      if ( GetLastError() == 183 || (v133 = MapViewOfFile(FileMappingW, 2u, 0, 0, 4u)) == 0 )
        CloseHandle(FileMappingW);
      else
        *v133 = 1;
    }
  }
  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    v211 = 0;
    TraceInitFabric(L"Get RgClient Job Handle.\r\n");
    RgClient_GetNtJobHandle(&v211);
    SOS_OS_NtJobObjectHandle = v211;
  }
  if ( !BlobAccess_FileSystemInit() )
  {
    scierrlog(0x42F2u, L"BlobAccess_FileSystemInit");
    SQLExit(55);
  }
  if ( OsInfo::IsLinux(SOS_OS_OsInfo) )
  {
    if ( *((_BYTE *)&g_featureSwitchesDk + 100) )
    {
      if ( (*(_BYTE *)(qword_10049F340 + 1112) & 2) == 0 )
      {
        LibraryW = LoadLibraryW(L"dkdll.dll");
        if ( !LibraryW
          || (g_SwitchPowerSavingModeFnPtr = (int (*)(bool))GetProcAddress(LibraryW, "NtSwitchPowerSavingMode")) == 0 )
        {
          v135 = GetLastError();
          if ( v135 )
            LogSystemMetadata(L"SetSwitchPowerSavingModeFnPtr failed. ErrorCode: %d.\n", v135);
        }
      }
    }
  }
  if ( (!v203 && v204 || v205) && *((_DWORD *)qword_10049F360 + 3626) )
  {
    v136 = (InstanceConfigStoreManager *)InstanceConfigStoreManager::GetInstanceConfigStoreManager();
    PropertyBagComplete = InstanceConfigStoreManager::GetPropertyBagComplete(v136, 0xAu);
    LogSystemMetadata(L"InstanceConfigStore initial startup get completed with code: %d.\n", PropertyBagComplete);
    v138 = (InstanceConfigStoreManager *)InstanceConfigStoreManager::GetInstanceConfigStoreManager();
    InstanceConfigStoreManager::ParsePropertyBagStartup(v138);
  }
  CaptureStartupPhaseTelemetry::CaptureStartupPhaseTelemetry((CaptureStartupPhaseTelemetry *)v229, 1);
  ConfigureDK();
  CaptureStartupPhaseTelemetry::~CaptureStartupPhaseTelemetry((CaptureStartupPhaseTelemetry *)v229);
  CaptureStartupPhaseTelemetry::CaptureStartupPhaseTelemetry((CaptureStartupPhaseTelemetry *)v230, 2);
  v139 = SOS_OS::Boot();
  CaptureStartupPhaseTelemetry::~CaptureStartupPhaseTelemetry((CaptureStartupPhaseTelemetry *)v230);
  if ( v139 )
  {
    scierrlog(0x42F2u, L"SQL OS Boot");
    SQLExit(56);
  }
  v140 = qword_10049F360;
  if ( !*((_DWORD *)qword_10049F360 + 3626) )
  {
    if ( *((_DWORD *)qword_10049F360 + 3629) )
    {
      if ( !*((_DWORD *)qword_10049F360 + 3624) )
        goto LABEL_255;
      if ( !*((_DWORD *)qword_10049F360 + 3625) )
      {
        if ( (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) == 2
          || (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) == 3 )
        {
LABEL_260:
          v140 = qword_10049F360;
          goto LABEL_261;
        }
LABEL_255:
        if ( (*(_BYTE *)(qword_10049F340 + 1197) & 0x20) == 0 )
          v95 = ((*(_BYTE *)(qword_10049F340 + 1198) & 2) != 0) | 2;
        *((_DWORD *)GetHadrGlobals() + 2) = v95;
        *(_DWORD *)GetHadrGlobals() = 1;
        if ( (*(_BYTE *)(qword_10049F340 + 1199) & 4) != 0 )
          *((_WORD *)GetHadrGlobals() + 2) = 8088;
        v141 = GetErrorReportingManager();
        LOBYTE(v142) = 1;
        (*(void (__fastcall **)(struct IErrorReportingManager *, const wchar_t *, __int64, __int64, int))(*(_QWORD *)v141 + 168LL))(
          v141,
          L"Enabling HADR for this XCluster instance. May not work properly if prerequisites are not met.\n",
          94,
          v142,
          -1);
        goto LABEL_260;
      }
    }
LABEL_261:
    RESOURCE::InitFCIMembership(v140);
    v140 = qword_10049F360;
  }
  RESOURCE::InitSqlVdi(v140);
  v143 = GetErrorReportingManager();
  CErrorReportingManager::LogStartupCollation(v143, 0);
  StartUp::InitializeCallbacks();
  v144 = *(char **)&SOS_PublicGlobals::sm_osStatus;
  if ( (SOS_PublicGlobals::sm_osStatus & 0x1000) != 0 )
  {
    scierrlog(0x4401u, 8);
    v144 = *(char **)&SOS_PublicGlobals::sm_osStatus;
  }
  if ( *v144 < 0 )
  {
    v209 = 260;
    memset_0(v237, 0, 0x20Au);
    GetVerSpecificRootRegPath(v237, &v209);
    scierrlog(0x4402u, v237);
  }
  if ( SOS_OS_AffinityType == 1 )
  {
    SystemAffinity::SafeCopy(SOS_PublicGlobals::sm_AffinityMask, v234);
    v145 = SOS_PublicGlobals::sm_NodeManager[16];
    for ( i = 0; i < v145; ++i )
    {
      NodeAffinity = SystemAffinity::GetNodeAffinity(v234, v227, i);
      scierrlog(0x4301u, i, 16, *(_QWORD *)(NodeAffinity + 8));
    }
  }
  if ( FUseReplicatedServerContext() )
    v148 = (char *)qword_10049F360 + 28520;
  else
    v148 = (char *)qword_10049F360 + 14864;
  if ( *((unsigned int *)v148 + 3076) | ((unsigned __int64)*((unsigned int *)v148 + 3085) << 32) )
    scierrlog(0x4303u, 16);
  if ( (unsigned int)NonYieldSystemInformation::InitNonYieldSystemInformation(NonYieldSystemInformation::sm_NonYieldSystemInfo) )
    scierrlog(0x42F2u, L"Non-yield analysis object");
  CheckFileVersion(L"sqldk.dll");
  CheckFileVersion(L"sqlmin.dll");
  v150 = 15;
  if ( (*((_DWORD *)qword_10049F360 + 12127) & 0x2000) != 0
    || *(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance(v149) + 557)
    && *(_DWORD *)(GetXdbServerGlobals(v152, v151) + 13060)
    && *((_DWORD *)qword_10049F360 + 3626) )
  {
    v150 = 11;
  }
  InitServerComponents(255, v150, 0, 0, 0);
  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    StartUp::WaitForMasterDbReady();
    RgClient_StopETWTrace();
  }
  if ( *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 1169) )
  {
    v154 = *((_QWORD *)s_pServerConf + 3);
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *), _QWORD, _QWORD))(*(_QWORD *)v154 + 8LL))(
            v154,
            L"FeatureSwitches",
            L"PersistTempdbFileLayout",
            InstanceConfigStoreManager::InitializeInstanceConfigStoreManagerCallback,
            0,
            0) )
      traceprint(L"Failed to subscribe Instance Config Store on a feature switch change.\n");
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *), _QWORD, _QWORD))(*(_QWORD *)v154 + 8LL))(
            v154,
            L"FeatureSwitches",
            L"EnableInstanceConfigStore",
            InstanceConfigStoreManager::InitializeInstanceConfigStoreManagerCallback,
            0,
            0) )
      traceprint(L"Failed to subscribe Instance Config Store on a feature switch change.\n");
  }
  if ( *(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance(v153) + 81) )
    UpdateTraceFLagsOnManagedInstance();
  if ( *((_DWORD *)s_pServerConf + 3) != 1 && !*((_DWORD *)qword_10049F360 + 3626) )
    VerifyTrust();
  InitializeAlwaysEncrypted();
  if ( *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 561) || (*(_BYTE *)(qword_10049F340 + 1559) & 8) != 0 )
    InitializeExternalAuthorizationEngine();
  CFeatureSwitchesLangSvc::GetCurrentInstance();
  v220 = 4195111;
  v221 = 0;
  v223 = 0;
  v222 = 0;
  v224 = 0;
  if ( (unsigned int)SOS_OS::EnqueueTask(ServerSetup, 0, 2, &v212, -1) )
  {
    scierrlog(0x42E0u, L"sqlservr_main");
    SQLExit(58, 0, 2147942414LL);
  }
  else
  {
    SOS_Task::WaitForDone(v212, 0xFFFFFFFFLL, &v220);
    v155 = (__int64 *)v212;
    if ( _InterlockedExchangeAdd(v212 + 10, 0xFFFFFFFF) == 1 )
    {
      if ( v155[3] )
      {
        TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v155 + 2);
      }
      else
      {
        if ( *((_DWORD *)v155 + 46) == 2 )
        {
          v213 = (volatile signed __int64 *)(v155[20] + 4952);
          v156 = v213;
          v214 = 0;
          v157.QuadPart = 0;
          UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *(_DWORD *)v213 || _InterlockedCompareExchange64(v213, UniqueThread_low, 0) )
          {
            v159 = 0;
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v160 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset;
              if ( v160 && *(_QWORD *)(v160 + 272) == v160 )
                v159 = *(_QWORD *)(v160 + 256);
              if ( v159 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&PerformanceCount);
                  v157 = PerformanceCount;
                }
                else
                {
                  v157.QuadPart = MEMORY[0x7FFE0008];
                }
              }
            }
            if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
              Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v156, UniqueThread_low);
            else
              Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v156, v159, UniqueThread_low);
            if ( v159 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v217);
                v161 = v217;
              }
              else
              {
                v161.QuadPart = MEMORY[0x7FFE0008];
              }
              v162 = v161.QuadPart - v157.QuadPart;
              if ( v161.QuadPart < (unsigned __int64)v157.QuadPart )
                v162 = 0;
              *(_QWORD *)(v159 + 3192) += v162;
            }
          }
          v214 = 1;
          v163 = (_QWORD *)v155[1];
          v164 = *v155;
          *(_QWORD *)(v164 + 8) = v163;
          *v163 = v164;
          v155[1] = 0;
          *v155 = 0;
          v165 = v213;
          if ( v213 )
          {
            if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
            {
              v166 = rand();
              if ( v166 == 5 * (v166 / 5) )
                Spinlock<11,2,268435714>::UpdateStatSnapshot();
            }
            *v165 = 0;
            v213 = 0;
            v214 = 0;
          }
        }
        v167 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v167
          && *(_QWORD *)(v167 + 272) == v167
          && (v168 = *(_QWORD *)(v167 + 256)) != 0
          && *(__int64 **)(v168 + 528) == v155 )
        {
          if ( v155 )
            v2 = v155 - 1;
          *v2 = (__int64)&ISOSHost_TaskImpl::`vftable';
          v169 = v2 + 1;
          v206 = v169;
          v170 = v169[22];
          if ( v170 )
          {
            if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
            {
              _InterlockedDecrement((volatile signed __int32 *)(v170 + 112));
              v170 = v169[22];
            }
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v170 + 24), 0xFFFFFFFF) == 1 )
            {
              if ( *(_QWORD *)(v170 + 8) )
                TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v170 + 16), v170);
              SOSHost::Destroy((SOSHost *)v170);
            }
          }
        }
        else
        {
          v171 = (SOS_Node *)v155[21];
          if ( v171 && *((_QWORD *)v171 + 30) && !SOS_Node::IsTaskStoreDisabled(v171) )
          {
            v172 = *(_QWORD *)(v155[21] + 240);
            v173 = v155 - 1;
            if ( !v155 )
              v173 = 0;
            *v173 = (__int64)&ISOSHost_TaskImpl::`vftable';
            v174 = v173 + 1;
            v206 = v174;
            v175 = v174[22];
            if ( v175 )
            {
              if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
              {
                _InterlockedDecrement((volatile signed __int32 *)(v175 + 112));
                v175 = v174[22];
              }
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v175 + 24), 0xFFFFFFFF) == 1 )
              {
                if ( *(_QWORD *)(v175 + 8) )
                  TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v175 + 16), v175);
                SOSHost::Destroy((SOSHost *)v175);
              }
            }
            v176 = v155 - 1;
            if ( !v155 )
              v176 = 0;
            v177 = *(_QWORD *)(v172 + 2016);
            v178.QuadPart = 0;
            v179 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
            if ( *(_DWORD *)(v177 + 40)
              || _InterlockedCompareExchange64((volatile signed __int64 *)(v177 + 40), v179, 0) )
            {
              v180 = 0;
              if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
              {
                v181 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset;
                if ( v181 && *(_QWORD *)(v181 + 272) == v181 )
                  v180 = *(_QWORD *)(v181 + 256);
                if ( v180 )
                {
                  if ( Base_PublicGlobals::sm_invariantTscAvailable )
                  {
                    QueryPerformanceCounter(&v218);
                    v178 = v218;
                  }
                  else
                  {
                    v178.QuadPart = MEMORY[0x7FFE0008];
                  }
                }
              }
              v182 = v177 + 40;
              if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v182, v179);
              else
                Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v182, v180, v179);
              if ( v180 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v219);
                  v183 = v219;
                }
                else
                {
                  v183.QuadPart = MEMORY[0x7FFE0008];
                }
                v184 = v183.QuadPart - v178.QuadPart;
                if ( v183.QuadPart < (unsigned __int64)v178.QuadPart )
                  v184 = 0;
                *(_QWORD *)(v180 + 3192) += v184;
              }
            }
            if ( *(_QWORD *)(v177 + 8) >= *(_QWORD *)v177 )
            {
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v193 = rand();
                if ( v193 == 5 * (v193 / 5) )
                  Spinlock<34,1,268435714>::UpdateStatSnapshot();
              }
              *(_QWORD *)(v177 + 40) = 0;
              (*(void (__fastcall **)(__int64 *))(v177 + 48))(v176);
            }
            else
            {
              if ( *(_BYTE *)(*(_QWORD *)(v177 + 32) + 5820LL) )
              {
                v185 = (__int64 *)(v177 + 16 * ((*(_DWORD *)(v177 + 1176) & 0x3F) + 9LL));
                *v176 = *v185;
                if ( !*v185 )
                  v185[1] = (__int64)v176;
                *v185 = (__int64)v176;
                ++*(_QWORD *)(v177 + 1176);
                VirtualProtect(v176, 0x1000u, 1u, &flOldProtect);
              }
              else
              {
                *v176 = *(_QWORD *)(v177 + 128);
                if ( !*(_QWORD *)(v177 + 128) )
                  *(_QWORD *)(v177 + 136) = v176;
                *(_QWORD *)(v177 + 128) = v176;
              }
              v186 = *(_QWORD *)(v177 + 1168) + 1LL;
              ++*(_QWORD *)(v177 + 8);
              v187 = *(SOS_ObjectStore **)(v177 + 32);
              if ( !*((_BYTE *)v187 + 5820) && v186 >= 0x20 )
              {
                PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v187, (struct SList *)v176);
                v189 = *(_QWORD *)(v177 + 128);
                v190 = *(_QWORD **)(v177 + 136);
                if ( v190 != (_QWORD *)(v177 + 128) && v190 )
                {
                  *v190 = *(_QWORD *)(v177 + 8 * PoolIdForObject + 1184);
                  *(_QWORD *)(v177 + 8 * PoolIdForObject + 1184) = v189;
                }
                *(_QWORD *)(v177 + 128) = 0;
                *(_QWORD *)(v177 + 136) = v177 + 128;
                v186 = 0;
                v191 = *(_QWORD *)(v177 + 1696);
                if ( ((1LL << PoolIdForObject) & v191) == 0 )
                  *(_QWORD *)(v177 + 1696) = v191 | (1LL << PoolIdForObject);
              }
              *(_QWORD *)(v177 + 1168) = v186;
              if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v192 = rand();
                if ( v192 == 5 * (v192 / 5) )
                  Spinlock<34,1,268435714>::UpdateStatSnapshot();
              }
              *(_QWORD *)(v177 + 40) = 0;
            }
          }
          else if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
          {
            v194 = v155 - 1;
            if ( !v155 )
              v194 = 0;
            VirtualFree(v194, 0, 0x8000u);
          }
          else if ( v155 )
          {
            v195 = v155 == (__int64 *)8;
            v196 = v155 - 1;
            v206 = v196;
            if ( !v195 )
            {
              *v196 = (__int64)&ISOSHost_TaskImpl::`vftable';
              v206 = v196 + 1;
              v197 = v196[23];
              if ( v197 )
              {
                if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
                {
                  _InterlockedDecrement((volatile signed __int32 *)(v197 + 112));
                  v197 = v196[23];
                }
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v197 + 24), 0xFFFFFFFF) == 1 )
                {
                  if ( *(_QWORD *)(v197 + 8) )
                    TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v197 + 16), v197);
                  SOSHost::Destroy((SOSHost *)v197);
                }
              }
              operator delete(v196, 0x3E0u);
            }
          }
        }
      }
    }
  }
  if ( *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 758) && !InitPolarisBackgroundTasks() )
  {
    scierrlog(0x408Du);
    SQLExit(303);
  }
  if ( *(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance(v198) + 694) )
  {
    v199 = InstanceHistoryStoreManager::StaticInit();
    LogSystemMetadata(L"Instance History Store Manager initialization completed with code: %d.\n", v199);
  }
}

```

## disassembly

```asm
0x100416770  push    rbp
0x100416772  push    r12
0x100416774  push    r13
0x100416776  push    r14
0x100416778  push    r15
0x10041677a  lea     rbp, [rsp-6F40h]
0x100416782  mov     eax, 7040h
0x100416787  call    _alloca_probe
0x10041678c  sub     rsp, rax
0x10041678f  mov     [rbp+6F60h+var_6F98], 0FFFFFFFFFFFFFFFEh
0x100416797  mov     [rsp+7060h+arg_0], rbx
0x10041679f  mov     [rsp+7060h+arg_8], rsi
0x1004167a7  mov     [rsp+7060h+arg_10], rdi
0x1004167af  mov     rax, cs:__security_cookie
0x1004167b6  xor     rax, rsp
0x1004167b9  mov     [rbp+6F60h+var_30], rax
0x1004167c0  mov     edx, 100h
0x1004167c5  lea     rcx, qword_1004A1720
0x1004167cc  call    cs:__imp_?Execute@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@W4DkParameterFlags@@@Z; DkParametersProcessor::Execute(DkParameterFlags)
0x1004167d2  mov     ebx, eax
0x1004167d4  test    eax, eax
0x1004167d6  jz      short loc_1004167EB
0x1004167d8  call    ?InitializeErrorReportingForStartupFailure@@YAXXZ; InitializeErrorReportingForStartupFailure(void)
0x1004167dd  lea     rdx, qword_1004A1720
0x1004167e4  mov     ecx, ebx
0x1004167e6  call    ?LogInvalidParameterInCommandLine@@YAXW4DkParameterErrorEnum@@AEBVDkParametersProcessor@@@Z; LogInvalidParameterInCommandLine(DkParameterErrorEnum,DkParametersProcessor const &)
0x1004167eb  call    ?IsXCopySetupInstance@@YAHXZ; IsXCopySetupInstance(void)
0x1004167f0  lea     rcx, Value; "True"
0x1004167f7  xor     esi, esi
0x1004167f9  mov     edx, esi
0x1004167fb  test    eax, eax
0x1004167fd  cmovnz  rdx, rcx; lpValue
0x100416801  lea     rcx, Name; "__MSSQL_XCOPY_SETUP"
0x100416808  call    cs:__imp_SetEnvironmentVariableW
0x10041680e  mov     rax, cs:qword_10049F360
0x100416815  cmp     [rax+38A8h], esi
0x10041681b  jz      short loc_100416835
0x10041681d  mov     rax, cs:qword_10049F340
0x100416824  cmp     [rax+453h], sil
0x10041682b  jl      short loc_100416835
0x10041682d  xor     ecx, ecx
0x10041682f  call    cs:__imp_RgClient_InitETWTrace
0x100416835  mov     r14d, 1
0x10041683b  mov     edx, r14d
0x10041683e  lea     rcx, ?clientProcessConfig@@3V?$SOS_ProcessConfigImpl@$00@@A; SOS_ProcessConfigImpl<1> clientProcessConfig
0x100416845  call    cs:__imp_?RegisterProcess@SOS_OS@@SA?AW4SOS_RESULT@@PEAVProcessConfig@@W4SOS_CallerType@@@Z; SOS_OS::RegisterProcess(ProcessConfig *,SOS_CallerType)
0x10041684b  test    eax, eax
0x10041684d  jz      short loc_10041686A
0x10041684f  lea     rdx, aRegisterwithso; "RegisterWithSOS"
0x100416856  mov     ecx, 42F2h; unsigned int
0x10041685b  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100416860  lea     ecx, [r14+2Dh]
0x100416864  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@@Z; SQLExit(SQLEXITCODE)
0x10041686a  call    cs:__imp_?PreBoot@SOS_OS@@SA?AW4SOS_RESULT@@XZ; SOS_OS::PreBoot(void)
0x100416870  test    eax, eax
0x100416872  jz      short loc_100416894
0x100416874  mov     ecx, 42AFh; unsigned int
0x100416879  call    ?LogStartupFailure@@YAXI@Z; LogStartupFailure(uint)
0x10041687e  mov     ecx, 410h
0x100416883  call    cs:__imp_?KillProcess@SOS_OS@@SAXK@Z; SOS_OS::KillProcess(ulong)
0x100416889  mov     ecx, 2Fh ; '/'
0x10041688e  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@@Z; SQLExit(SQLEXITCODE)
0x100416894  xor     r9d, r9d; lpName
0x100416897  xor     r8d, r8d; bInitialState
0x10041689a  xor     edx, edx; bManualReset
0x10041689c  xor     ecx, ecx; lpEventAttributes
0x10041689e  call    cs:__imp_CreateEventW
0x1004168a4  mov     rdi, rax
0x1004168a7  test    rax, rax
0x1004168aa  jnz     short loc_100416914
0x1004168ac  call    cs:__imp_GetLastError
0x1004168b2  mov     ebx, eax
0x1004168b4  test    eax, eax
0x1004168b6  jle     short loc_1004168C1
0x1004168b8  movzx   ebx, ax
0x1004168bb  or      ebx, 80070000h
0x1004168c1  test    ebx, ebx
0x1004168c3  jns     short loc_100416914
0x1004168c5  lfence
0x1004168c8  mov     ecx, ebx
0x1004168ca  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x1004168d0  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x1004168d6  mov     r9, rax; struct __crt_locale_pointers *
0x1004168d9  mov     dword ptr [rsp+7060h+lpThreadId], ebx
0x1004168dd  lea     rbx, aDcomCreateeven; "DCOM CreateEvent failure."
0x1004168e4  mov     qword ptr [rsp+7060h+dwCreationFlags], rbx
0x1004168e9  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x1004168f0  mov     edx, 200h; unsigned __int64
0x1004168f5  lea     rcx, [rbp+6F60h+var_6430]; Buffer
0x1004168fc  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x100416901  test    eax, eax
0x100416903  mov     rcx, rbx
0x100416906  js      short loc_10041690F
0x100416908  lea     rcx, [rbp+6F60h+var_6430]; char *
0x10041690f  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100416914  mov     [rsp+7060h+lpThreadId], rsi; lpThreadId
0x100416919  mov     [rsp+7060h+dwCreationFlags], esi; dwCreationFlags
0x10041691d  mov     r9, rdi; lpParameter
0x100416920  lea     r8, ?DCOMInitThread@@YAKPEAX@Z; lpStartAddress
0x100416927  xor     edx, edx; dwStackSize
0x100416929  xor     ecx, ecx; lpThreadAttributes
0x10041692b  call    cs:__imp_CreateThread
0x100416931  test    rax, rax
0x100416934  jnz     short loc_1004169A7
0x100416936  call    cs:__imp_GetLastError
0x10041693c  mov     ebx, eax
0x10041693e  test    eax, eax
0x100416940  jle     short loc_10041694B
0x100416942  movzx   ebx, ax
0x100416945  or      ebx, 80070000h
0x10041694b  test    ebx, ebx
0x10041694d  jns     short loc_1004169B0
0x10041694f  lfence
0x100416952  mov     ecx, ebx
0x100416954  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x10041695a  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100416960  mov     r9, rax; struct __crt_locale_pointers *
0x100416963  mov     dword ptr [rsp+7060h+lpThreadId], ebx
0x100416967  lea     rbx, aDcomCreatethre; "DCOM CreateThread failure."
0x10041696e  mov     qword ptr [rsp+7060h+dwCreationFlags], rbx
0x100416973  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x10041697a  mov     edx, 200h; unsigned __int64
0x10041697f  lea     rcx, [rbp+6F60h+var_6230]; Buffer
0x100416986  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x10041698b  test    eax, eax
0x10041698d  jns     short loc_100416999
0x10041698f  mov     rcx, rbx; char *
0x100416992  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100416997  jmp     short loc_1004169B0
0x100416999  lea     rcx, [rbp+6F60h+var_6230]; char *
0x1004169a0  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x1004169a5  jmp     short loc_1004169B0
0x1004169a7  mov     rcx, rax; hObject
0x1004169aa  call    cs:__imp_CloseHandle
0x1004169b0  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x1004169b5  mov     rcx, rdi; hHandle
0x1004169b8  call    cs:__imp_WaitForSingleObject
0x1004169be  mov     rcx, rdi; hObject
0x1004169c1  call    cs:__imp_CloseHandle
0x1004169c7  xor     edx, edx
0x1004169c9  lea     rcx, [rbp+6F60h+var_6F30]
0x1004169cd  call    cs:__imp_??0CaptureStartupPhaseTelemetry@@QEAA@H@Z; CaptureStartupPhaseTelemetry::CaptureStartupPhaseTelemetry(int)
0x1004169d3  nop
0x1004169d4  mov     r9d, 800h; unsigned __int64
0x1004169da  lea     r8, [rbp+6F60h+var_4030]; wchar_t *
0x1004169e1  mov     edx, r9d; unsigned __int64
0x1004169e4  lea     rcx, [rbp+6F60h+var_5030]; wchar_t *
0x1004169eb  call    ?InitFabric@@YAJPEA_W_K01@Z; InitFabric(wchar_t *,unsigned __int64,wchar_t *,unsigned __int64)
0x1004169f0  mov     ebx, eax
0x1004169f2  test    eax, eax
0x1004169f4  jns     short loc_100416A46
0x1004169f6  lfence
0x1004169f9  mov     ecx, eax
0x1004169fb  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x100416a01  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100416a07  mov     r9, rax; struct __crt_locale_pointers *
0x100416a0a  mov     dword ptr [rsp+7060h+lpThreadId], ebx
0x100416a0e  lea     rbx, aXdbHostRegistr; "XDB Host registration failure."
0x100416a15  mov     qword ptr [rsp+7060h+dwCreationFlags], rbx
0x100416a1a  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x100416a21  mov     edx, 200h; unsigned __int64
0x100416a26  lea     rcx, [rbp+6F60h+var_6030]; Buffer
0x100416a2d  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x100416a32  test    eax, eax
0x100416a34  mov     rcx, rbx
0x100416a37  js      short loc_100416A40
0x100416a39  lea     rcx, [rbp+6F60h+var_6030]; char *
0x100416a40  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100416a45  nop
0x100416a46  lea     rcx, [rbp+6F60h+var_6F30]
0x100416a4a  call    cs:__imp_??1CaptureStartupPhaseTelemetry@@QEAA@XZ; CaptureStartupPhaseTelemetry::~CaptureStartupPhaseTelemetry(void)
0x100416a50  mov     [rsp+7060h+var_702F], 0
0x100416a55  xor     bl, bl
0x100416a57  mov     [rsp+7060h+var_702D], bl
0x100416a5b  mov     [rsp+7060h+var_702E], bl
0x100416a5f  xor     cl, cl
0x100416a61  mov     [rsp+7060h+var_702C], cl
0x100416a65  mov     rax, cs:qword_10049F360
0x100416a6c  cmp     dword ptr [rax+38A8h], 0
0x100416a73  jz      loc_100416B4F
0x100416a79  lea     r8, [rsp+7060h+var_702F]
0x100416a7e  lea     rdx, aEnableinstance; "EnableInstanceConfigStore"
0x100416a85  lea     rcx, aSqlConfig; "SQL.Config"
0x100416a8c  call    cs:__imp_HostReg_IsFeatureSwitchOn
0x100416a92  movzx   ebx, al
0x100416a95  mov     [rsp+7060h+var_702D], al
0x100416a99  lea     r8, [rsp+7060h+var_702F]
0x100416a9e  lea     rdx, aEnablereplicai; "EnableReplicaInfoCacheForAuxiliaryRepli"...
0x100416aa5  lea     rcx, aSqlConfig; "SQL.Config"
0x100416aac  call    cs:__imp_HostReg_IsFeatureSwitchOn
0x100416ab2  movzx   edi, al
0x100416ab5  mov     [rsp+7060h+var_702E], al
0x100416ab9  lea     r8, [rsp+7060h+var_702F]
0x100416abe  lea     rdx, aPersisttempdbf; "PersistTempdbFileLayout"
0x100416ac5  lea     rcx, aSqlConfig; "SQL.Config"
0x100416acc  call    cs:__imp_HostReg_IsFeatureSwitchOn
0x100416ad2  mov     [rsp+7060h+var_702C], al
0x100416ad6  test    dil, dil
0x100416ad9  jnz     short loc_100416ADF
0x100416adb  test    bl, bl
0x100416add  jnz     short loc_100416AE3
0x100416adf  test    al, al
0x100416ae1  jz      short loc_100416B4F
0x100416ae3  xor     ecx, ecx
0x100416ae5  call    cs:__imp_?StaticInit@InstanceConfigStoreManager@@SAJPEAVIRgIsolationSettingsUpdater@@@Z; InstanceConfigStoreManager::StaticInit(IRgIsolationSettingsUpdater *)
0x100416aeb  mov     ebx, eax
0x100416aed  test    eax, eax
0x100416aef  jns     short loc_100416B40
0x100416af1  lfence
0x100416af4  mov     ecx, eax
0x100416af6  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x100416afc  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100416b02  mov     r9, rax; struct __crt_locale_pointers *
0x100416b05  mov     dword ptr [rsp+7060h+lpThreadId], ebx
0x100416b09  lea     rbx, aInstanceConfig; "Instance Config Store Manager failure."
0x100416b10  mov     qword ptr [rsp+7060h+dwCreationFlags], rbx
0x100416b15  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x100416b1c  mov     edx, 200h; unsigned __int64
0x100416b21  lea     rcx, [rbp+6F60h+var_5E30]; Buffer
0x100416b28  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x100416b2d  test    eax, eax
0x100416b2f  mov     rcx, rbx
0x100416b32  js      short loc_100416B3B
0x100416b34  lea     rcx, [rbp+6F60h+var_5E30]; char *
0x100416b3b  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100416b40  call    cs:__imp_?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ; InstanceConfigStoreManager::GetInstanceConfigStoreManager(void)
0x100416b46  mov     rcx, rax
0x100416b49  call    cs:__imp_?GetPropertyBagStart@InstanceConfigStoreManager@@QEAAJXZ; InstanceConfigStoreManager::GetPropertyBagStart(void)
0x100416b4f  cmp     [rbp+6F60h+var_5030], 0
0x100416b57  jz      short loc_100416B89
0x100416b59  mov     r8b, 1
0x100416b5c  lea     rdx, [rbp+6F60h+var_5030]
0x100416b63  lea     rcx, qword_1004A1720
0x100416b6a  call    cs:__imp_?ProcessBuffer@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@PEB_W_N@Z; DkParametersProcessor::ProcessBuffer(wchar_t const *,bool)
0x100416b70  mov     ebx, eax
0x100416b72  test    eax, eax
0x100416b74  jz      short loc_100416B89
0x100416b76  call    ?InitializeErrorReportingForStartupFailure@@YAXXZ; InitializeErrorReportingForStartupFailure(void)
0x100416b7b  lea     rdx, qword_1004A1720
0x100416b82  mov     ecx, ebx
0x100416b84  call    ?LogInvalidParameterInCommandLine@@YAXW4DkParameterErrorEnum@@AEBVDkParametersProcessor@@@Z; LogInvalidParameterInCommandLine(DkParameterErrorEnum,DkParametersProcessor const &)
0x100416b89  cmp     [rbp+6F60h+var_4030], 0
0x100416b91  jz      short loc_100416BC3
0x100416b93  mov     r8b, 1
0x100416b96  lea     rdx, [rbp+6F60h+var_4030]
0x100416b9d  lea     rcx, qword_1004A17A0
0x100416ba4  call    cs:__imp_?ProcessBuffer@DkParametersProcessor@@QEAA?AW4DkParameterErrorEnum@@PEB_W_N@Z; DkParametersProcessor::ProcessBuffer(wchar_t const *,bool)
0x100416baa  mov     ebx, eax
0x100416bac  test    eax, eax
0x100416bae  jz      short loc_100416BC3
0x100416bb0  call    ?InitializeErrorReportingForStartupFailure@@YAXXZ; InitializeErrorReportingForStartupFailure(void)
0x100416bb5  lea     rdx, qword_1004A17A0
0x100416bbc  mov     ecx, ebx
0x100416bbe  call    ?LogInvalidParameterInCommandLine@@YAXW4DkParameterErrorEnum@@AEBVDkParametersProcessor@@@Z; LogInvalidParameterInCommandLine(DkParameterErrorEnum,DkParametersProcessor const &)
0x100416bc3  mov     r15d, esi
0x100416bc6  call    cs:__imp_GetXdbServerGlobals
0x100416bcc  mov     r13d, 105h
0x100416bd2  cmp     [rax+2EC8h], esi
0x100416bd8  jz      loc_100416CDA
0x100416bde  call    cs:__imp_GetXdbServerGlobals
0x100416be4  cmp     [rax+599Ch], r15b
0x100416beb  jz      loc_100416CDA
0x100416bf1  call    cs:__imp_GetXdbServerGlobals
0x100416bf7  lea     rcx, [rax+599Eh]; wchar_t *
0x100416bfe  call    ?InitCLDetours@@YAJPEB_W@Z; InitCLDetours(wchar_t const *)
0x100416c03  test    eax, eax
0x100416c05  jnz     short loc_100416C12
0x100416c07  call    cs:__imp_?SetDualTimeZoneSqlErrorReportingManager@@YAXXZ; SetDualTimeZoneSqlErrorReportingManager(void)
0x100416c0d  jmp     loc_100416CDA
0x100416c12  mov     r15d, eax
0x100416c15  call    cs:__imp_GetXdbServerGlobals
0x100416c1b  lea     r8, [rax+599Eh]
0x100416c22  mov     rbx, r13
0x100416c25  lea     rdx, [rbp+6F60h+var_6910]
0x100416c2c  lea     rax, [rbp+6F60h+var_6910]
0x100416c33  sub     r8, rax
0x100416c36  nop     word ptr [rax+rax+00000000h]
0x100416c40  lea     rcx, [rbx+7FFFFEF9h]
0x100416c47  test    rcx, rcx
0x100416c4a  jz      short loc_100416C63
0x100416c4c  movzx   eax, word ptr [r8+rdx]
0x100416c51  test    ax, ax
0x100416c54  jz      short loc_100416C63
0x100416c56  mov     [rdx], ax
0x100416c59  add     rdx, 2
0x100416c5d  sub     rbx, 1
0x100416c61  jnz     short loc_100416C40
0x100416c63  lea     rax, [rdx-2]
0x100416c67  test    rbx, rbx
0x100416c6a  cmovnz  rax, rdx
0x100416c6e  mov     [rax], si
0x100416c71  mov     edi, 8007007Ah
0x100416c76  cmovnz  edi, esi
0x100416c79  call    cs:__imp_GetXdbServerGlobals
0x100416c7f  mov     byte ptr [rax+599Ch], 0
0x100416c86  test    rbx, rbx
0x100416c89  jnz     short loc_100416CDA
0x100416c8b  lfence
0x100416c8e  mov     ecx, edi
0x100416c90  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
  ... truncated ...
```

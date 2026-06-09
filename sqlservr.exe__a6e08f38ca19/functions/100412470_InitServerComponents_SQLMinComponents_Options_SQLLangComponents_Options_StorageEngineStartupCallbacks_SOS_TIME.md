# InitServerComponents(SQLMinComponents::Options,SQLLangComponents::Options,StorageEngineStartupCallbacks *,SOS_TIMERRESULT (*)(void *,ulong *,ulong *),SOS_TIMERRESULT (*)(void *))

- ea: `0x100412470`
- end: `0x100413d06`
- name: `?InitServerComponents@@YAXW4Options@SQLMinComponents@@W41SQLLangComponents@@PEAUStorageEngineStartupCallbacks@@P6A?AW4SOS_TIMERRESULT@@PEAXPEAK4@ZP6A?AW45@3@Z@Z`
- size: `6294`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100416770`

## callees

- `0x100401580`
- `0x100402ec0`
- `0x100404a30`
- `0x100408320`
- `0x100408560`
- `0x100408810`
- `0x10040a080`
- `0x10040d2a0`
- `0x10040d5d0`
- `0x100412470`
- `0x100415b60`
- `0x10041d7e0`
- `0x10041d870`
- `0x10041df30`
- `0x10041e170`
- `0x10041e420`
- `0x10041e540`
- `0x10041e640`
- `0x10041e8e0`
- `0x10041eac0`
- `0x10042a380`
- `0x10043a840`
- `0x10043b680`
- `0x10043f6a0`
- `0x10043ffc0`
- `0x1004403d0`
- `0x1004404f0`
- `0x100440570`
- `0x100440860`
- `0x10044aad0`
- `0x10044e410`
- `0x100452b78`
- `0x100452be0`

## import_xrefs

- `NETAPI32!NetUserModalsSet` at `0x100413a5c`
- `NETAPI32!NetUserModalsSet` at `0x100413a80`
- `NETAPI32!NetUserModalsSet` at `0x100413a5c`
- `NETAPI32!NetUserModalsSet` at `0x100413a80`
- `KERNEL32!SetEnvironmentVariableW` at `0x100413677`
- `KERNEL32!SetEnvironmentVariableW` at `0x10041369b`
- `KERNEL32!SetEnvironmentVariableW` at `0x1004136db`
- `KERNEL32!SetEnvironmentVariableW` at `0x100413677`
- `KERNEL32!SetEnvironmentVariableW` at `0x10041369b`
- `KERNEL32!SetEnvironmentVariableW` at `0x1004136db`
- `KERNEL32!VirtualProtect` at `0x10041303f`
- `KERNEL32!VirtualProtect` at `0x10041303f`
- `KERNEL32!GetLastError` at `0x1004136e5`
- `KERNEL32!GetLastError` at `0x1004136e5`
- `KERNEL32!QueryPerformanceCounter` at `0x100412c7e`
- `KERNEL32!QueryPerformanceCounter` at `0x100412ccf`
- `KERNEL32!QueryPerformanceCounter` at `0x100412f68`
- `KERNEL32!QueryPerformanceCounter` at `0x100412fba`
- `KERNEL32!QueryPerformanceCounter` at `0x100412c7e`
- `KERNEL32!QueryPerformanceCounter` at `0x100412ccf`
- `KERNEL32!QueryPerformanceCounter` at `0x100412f68`
- `KERNEL32!QueryPerformanceCounter` at `0x100412fba`
- `KERNEL32!VirtualFree` at `0x1004131a3`
- `KERNEL32!VirtualFree` at `0x1004131a3`
- `sqlmin!?ExcludeFromDumpClerkTypeStringCallBack@ClerkConfig@@SAXPEB_W00PEAX@Z` at `0x100413cab`
- `sqlmin!?ParseRgInstanceLevelSloPropertyBag@RESOURCE@@QEAAJXZ` at `0x100413c4f`
- `sqlmin!?ParseRgInstanceLevelSloPropertyBag@RESOURCE@@QEAAJXZ` at `0x100413c4f`
- `sqlmin!?SQLMinInitComponents@@YAXKPEAVIFTServiceMgr@@AEAUStorageEngineStartupCallbacks@@W4Options@SQLMinComponents@@W43SQLLangComponents@@PEA_WPEAUNonYieldingConfigurationFunctions@@@Z` at `0x1004135e7`
- `sqlmin!?SQLMinInitComponents@@YAXKPEAVIFTServiceMgr@@AEAUStorageEngineStartupCallbacks@@W4Options@SQLMinComponents@@W43SQLLangComponents@@PEA_WPEAUNonYieldingConfigurationFunctions@@@Z` at `0x1004135e7`
- `sqlmin!?SetOnDemandTaskCallBacks@@YAXP6A?AW4SOS_TIMERRESULT@@PEAXPEAK1@ZP6A?AW41@0@Z@Z` at `0x100413473`
- `sqlmin!?SetOnDemandTaskCallBacks@@YAXP6A?AW4SOS_TIMERRESULT@@PEAXPEAK1@ZP6A?AW41@0@Z@Z` at `0x100413473`
- `sqlmin!?OutputCpuInstructionSupport@SimdHelpers@@SAXPEBVSOS_CPUInstructionSupport@@@Z` at `0x100413430`
- `sqlmin!?OutputCpuInstructionSupport@SimdHelpers@@SAXPEBVSOS_CPUInstructionSupport@@@Z` at `0x100413430`
- `sqlmin!?InitLedgerAlg@@YAXXZ` at `0x100413423`
- `sqlmin!?InitLedgerAlg@@YAXXZ` at `0x100413423`
- `sqlmin!?StartFidoGLMManager@@YAJXZ` at `0x100413398`
- `sqlmin!?StartFidoGLMManager@@YAJXZ` at `0x100413398`
- `sqlmin!?InitHekatonXEPackages@@YAXXZ` at `0x1004132d6`
- `sqlmin!?InitHekatonXEPackages@@YAXXZ` at `0x1004132d6`
- `sqlmin!?SetAsCompleted@StartupDependencies@@SAXW4Components@1@@Z` at `0x100412af6`
- `sqlmin!?SetAsCompleted@StartupDependencies@@SAXW4Components@1@@Z` at `0x100412af6`
- `sqlmin!?ParsePropertyBag@InstanceConfigStoreManager@@QEAAXXZ` at `0x100412881`
- `sqlmin!?ParsePropertyBag@InstanceConfigStoreManager@@QEAAXXZ` at `0x100412881`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100412814`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100412878`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100412814`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100412878`
- `sqlmin!?PostInit@InstanceConfigStoreManager@@QEAAJXZ` at `0x10041281d`
- `sqlmin!?PostInit@InstanceConfigStoreManager@@QEAAJXZ` at `0x10041281d`
- `sqlmin!?Init@CFeatureSwitchesFido@@SAXW4CFeatureSwitchesExecEnv@@@Z` at `0x100412780`
- `sqlmin!?Init@CFeatureSwitchesFido@@SAXW4CFeatureSwitchesExecEnv@@@Z` at `0x100412780`
- `sqlmin!?Init@CFeatureSwitchesMin@@SAXW4CFeatureSwitchesExecEnv@@@Z` at `0x100412754`
- `sqlmin!?Init@CFeatureSwitchesMin@@SAXW4CFeatureSwitchesExecEnv@@@Z` at `0x100412754`
- `sqlmin!?InitXeForSqlmin@@YAXXZ` at `0x10041267c`
- `sqlmin!?InitXeForSqlmin@@YAXXZ` at `0x10041267c`
- `sqlmin!?GetReplicatedMasterDbId@@YAGXZ` at `0x100412531`
- `sqlmin!?GetReplicatedMasterDbId@@YAGXZ` at `0x100412531`
- `sqlmin!?SetMasterDbId@@YAXG@Z` at `0x10041253a`
- `sqlmin!?SetMasterDbId@@YAXG@Z` at `0x10041253a`
- `sqlmin!??1CaptureStartupPhaseTelemetry@@QEAA@XZ` at `0x10041269d`
- `sqlmin!??1CaptureStartupPhaseTelemetry@@QEAA@XZ` at `0x10041269d`
- `sqlmin!??0CaptureStartupPhaseTelemetry@@QEAA@H@Z` at `0x100412549`
- `sqlmin!??0CaptureStartupPhaseTelemetry@@QEAA@H@Z` at `0x100412549`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x1004127f6`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100412903`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10041292b`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100412b19`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100412b44`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100413c39`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x1004127f6`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100412903`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10041292b`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100412b19`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100412b44`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100413c39`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10041279a`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x1004127d0`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100413313`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100413340`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10041335f`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10041279a`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x1004127d0`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100413313`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100413340`
- `sqlmin!?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x10041335f`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100413436`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100413436`
- `sqlmin!GetXdbServerGlobals` at `0x1004124d0`
- `sqlmin!GetXdbServerGlobals` at `0x100412897`
- `sqlmin!GetXdbServerGlobals` at `0x100413224`
- `sqlmin!GetXdbServerGlobals` at `0x100413233`
- `sqlmin!GetXdbServerGlobals` at `0x100413242`
- `sqlmin!GetXdbServerGlobals` at `0x1004132b7`
- `sqlmin!GetXdbServerGlobals` at `0x1004132f5`
- `sqlmin!GetXdbServerGlobals` at `0x100413304`
- `sqlmin!GetXdbServerGlobals` at `0x100413389`
- `sqlmin!GetXdbServerGlobals` at `0x100413603`
- `sqlmin!GetXdbServerGlobals` at `0x10041397c`
- `sqlmin!GetXdbServerGlobals` at `0x10041398b`
- `sqlmin!GetXdbServerGlobals` at `0x1004139af`
- `sqlmin!GetXdbServerGlobals` at `0x100413bfd`
- `sqlmin!GetXdbServerGlobals` at `0x100413c0c`
- `sqlmin!GetXdbServerGlobals` at `0x100413c1b`
- `sqlmin!GetXdbServerGlobals` at `0x100413c2a`
- `sqlmin!GetXdbServerGlobals` at `0x1004124d0`
- `sqlmin!GetXdbServerGlobals` at `0x100412897`
- `sqlmin!GetXdbServerGlobals` at `0x100413224`
- `sqlmin!GetXdbServerGlobals` at `0x100413233`
- `sqlmin!GetXdbServerGlobals` at `0x100413242`
- `sqlmin!GetXdbServerGlobals` at `0x1004132b7`
- `sqlmin!GetXdbServerGlobals` at `0x1004132f5`
- `sqlmin!GetXdbServerGlobals` at `0x100413304`
- `sqlmin!GetXdbServerGlobals` at `0x100413389`
- `sqlmin!GetXdbServerGlobals` at `0x100413603`
- `sqlmin!GetXdbServerGlobals` at `0x10041397c`
- `sqlmin!GetXdbServerGlobals` at `0x10041398b`
- `sqlmin!GetXdbServerGlobals` at `0x1004139af`
- `sqlmin!GetXdbServerGlobals` at `0x100413bfd`
- `sqlmin!GetXdbServerGlobals` at `0x100413c0c`
- `sqlmin!GetXdbServerGlobals` at `0x100413c1b`
- `sqlmin!GetXdbServerGlobals` at `0x100413c2a`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x1004125ab`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10041282e`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x1004129da`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100412aa7`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x1004133a9`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100413703`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x1004137a8`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10041386d`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100413932`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x1004125ab`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10041282e`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x1004129da`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100412aa7`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x1004133a9`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100413703`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x1004137a8`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x10041386d`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100413932`
- `sqllang!?InitSUM@@YAXXZ` at `0x100413618`
- `sqllang!?InitSUM@@YAXXZ` at `0x100413618`
- `sqllang!?InitializeSFWLists@@YAXXZ` at `0x100413612`
- `sqllang!?InitializeSFWLists@@YAXXZ` at `0x100413612`
- `sqllang!?InitializeQDSComponent@@YAXXZ` at `0x1004135f7`
- `sqllang!?InitializeQDSComponent@@YAXXZ` at `0x1004135f7`
- `sqllang!?GetFullTextServiceMgr@@YAPEAVIFTServiceMgr@@XZ` at `0x1004135b3`
- `sqllang!?GetFullTextServiceMgr@@YAPEAVIFTServiceMgr@@XZ` at `0x1004135b3`
- `sqllang!?InitializeQdsIntrinsics@@YAXXZ` at `0x1004135ad`
- `sqllang!?InitializeQdsIntrinsics@@YAXXZ` at `0x1004135ad`
- `sqllang!?SQLLangInitComponents@@YAXPEBUSQLLangInitBlock@@@Z` at `0x10041358a`
- `sqllang!?SQLLangInitComponents@@YAXPEBUSQLLangInitBlock@@@Z` at `0x10041358a`
- `sqllang!?SetupOdsCallbacks@@YAXPEAUods_callbacks@@@Z` at `0x10041348f`
- `sqllang!?SetupOdsCallbacks@@YAXPEAUods_callbacks@@@Z` at `0x10041348f`
- `sqllang!?SystemTaskInit@@YA?AW4SOS_TIMERRESULT@@PEAX@Z` at `0x100413465`
- `sqllang!?SystemTaskEntryPoint@@YA?AW4SOS_TIMERRESULT@@PEAXPEAK1@Z` at `0x10041345a`
- `sqllang!?LoadCertificateAndAddToStore@@YAJPEB_W0@Z` at `0x1004128af`
- `sqllang!?LoadCertificateAndAddToStore@@YAJPEB_W0@Z` at `0x1004128af`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100412805`
- `sqllang!?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x100412805`
- `sqllang!?ExportCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x1004127c7`
- `sqllang!?ExportCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ` at `0x1004127c7`
- `sqllang!?SQLLangImportFeatureSwitches@@YAXPEBVCFeatureSwitchesMin@@PEBVCFeatureSwitchesQds@@@Z` at `0x1004127a6`
- `sqllang!?SQLLangImportFeatureSwitches@@YAXPEBVCFeatureSwitchesMin@@PEBVCFeatureSwitchesQds@@@Z` at `0x1004127a6`
- `sqllang!?Init@CFeatureSwitchesBluemoon@@SAXW4CFeatureSwitchesExecEnv@@@Z` at `0x10041278b`
- `sqllang!?Init@CFeatureSwitchesBluemoon@@SAXW4CFeatureSwitchesExecEnv@@@Z` at `0x10041278b`
- `sqllang!?Init@CFeatureSwitchesLangSvc@@SAXW4CFeatureSwitchesExecEnv@@@Z` at `0x100412775`
- `sqllang!?Init@CFeatureSwitchesLangSvc@@SAXW4CFeatureSwitchesExecEnv@@@Z` at `0x100412775`
- `sqllang!?Init@CFeatureSwitchesTds@@SAXW4CFeatureSwitchesExecEnv@@@Z` at `0x10041275f`
- `sqllang!?Init@CFeatureSwitchesTds@@SAXW4CFeatureSwitchesExecEnv@@@Z` at `0x10041275f`
- `sqllang!?InitAdhocXESessionSupport@@YAXXZ` at `0x100412676`
- `sqllang!?InitAdhocXESessionSupport@@YAXXZ` at `0x100412676`
- `sqllang!?InitXeForSqlLang@@YAX_N@Z` at `0x100412670`
- `sqllang!?InitXeForSqlLang@@YAX_N@Z` at `0x100412670`
- `sqllang!?ConfigureSecurityForStartup@@YAXXZ` at `0x100413528`
- `sqlTsEs!?Init@CFeatureSwitchesTsEs@@SAXW4CFeatureSwitchesExecEnv@@@Z` at `0x100412749`
- `sqlTsEs!?Init@CFeatureSwitchesTsEs@@SAXW4CFeatureSwitchesExecEnv@@@Z` at `0x100412749`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100412c92`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100412f7c`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100413c82`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1004126f5`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10041272a`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1004128d1`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10041328f`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100413c92`
- `sqldk!?sm_cpuInstructionSupport@SOS_PublicGlobals@@2VSOS_CPUInstructionSupport@@A` at `0x100413429`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100412527`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x100412527`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004129ae`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100412a5a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041377a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004129ae`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100412a5a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041377a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10041321e`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10041321e`
- `sqldk!SystemThread_TlsOffset` at `0x100412501`
- `sqldk!SystemThread_TlsOffset` at `0x100412993`
- `sqldk!SystemThread_TlsOffset` at `0x100412a3f`
- `sqldk!SystemThread_TlsOffset` at `0x100412c4a`
- `sqldk!SystemThread_TlsOffset` at `0x100412d73`

## string_xrefs

- `0x100412629`: `SQL.Config`
- `0x100412841`: `Instance Config Store Manager post initialization failed.`
- `0x100412aba`: `Failed to start completion ports threads`
- `0x1004129ed`: `Failed to initialize IOCompletionPortThreadPool`
- `0x100412b0d`: `%hs - IOCompletionPortThreadPool successfully started with %u threads.`
- `0x100412b06`: `InitServerComponents`
- `0x100413c5f`: `InitServerComponents`
- `0x100412b82`: `InitServerComponents`
- `0x10041384f`: `sqlagent.exe -c -xdb -wcowchild`
- `0x100413848`: `SqlAgent`
- `0x100413880`: `LaunchWcowSidecarProcess for SqlAgent failed.`
- `0x1004137fc`: `SqlAgent\sqlagent.exe`
- `0x100413945`: `LaunchWcowSidecarProcess for FdHost failed.`
- `0x100413c66`: `%hs - DW FIDO SloPropertyBag read and apply failed with hr = 0x%x .`
- `0x100413cc9`: `Failed to read ExcludeFromDumpClerkTypeString setting.`
- `0x100413aea`: `set deadlock_priority 10\nDECLARE @cmd1 nvarchar(max)\n\nIF NOT EXISTS (SELECT * FROM sys.server_principals WHERE name = N'NT AUTHORITY\SYSTEM')\nBEGIN\n	SELECT @cmd1 = 'CREATE LOGIN [NT AUTHORITY\SYSTEM] FROM WINDOWS'\n	EXEC (@cmd1)\n\n	EXEC sys.sp_dropsrvrolemember N'NT AUTHORITY\SYSTEM', N'sysadmin'\nEND\n`
- `0x1004136d4`: `Fabric_ServiceManifestName`
- `0x100413830`: `LaunchWcowSidecarProcess`
- `0x1004138f5`: `LaunchWcowSidecarProcess`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall InitServerComponents(
        __int64 a1,
        __int64 a2,
        void (**a3)(struct DBTABLE *, struct IMetadataAccess *, bool),
        enum SOS_TIMERRESULT (__high *a4)(void *, unsigned int *, unsigned int *),
        enum SOS_TIMERRESULT (__high *a5)(void *))
{
  enum SOS_TIMERRESULT (__high *v5)(void *, unsigned int *, unsigned int *); // rsi
  void (**v6)(struct DBTABLE *, struct IMetadataAccess *, bool); // r12
  int v7; // r15d
  enum SOS_TIMERRESULT (__high *v8)(void *); // r14
  __int64 v9; // rax
  struct CSessionTraceFlags *v10; // rcx
  unsigned __int16 ReplicatedMasterDbId; // ax
  ProcessConfig *v12; // rbx
  int (*const *IsEnabledCallbacks)(void); // rax
  void (*const *XeSosPublishCallbacks)(void *); // rax
  int (*const *IsCollectEventColumnEnabledCallbacks)(void); // rax
  signed int v16; // eax
  signed int v17; // ebx
  struct __crt_locale_pointers *DefaultLocale; // rax
  int v19; // eax
  char *v20; // rcx
  RESOURCE *v21; // rax
  int v22; // r13d
  RESOURCE *v23; // rax
  const struct CFeatureSwitchesQds *v24; // rbx
  const struct CFeatureSwitchesMin *v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rbx
  __int64 v29; // rax
  InstanceConfigStoreManager *InstanceConfigStoreManager; // rax
  signed int v31; // eax
  signed int v32; // ebx
  struct __crt_locale_pointers *v33; // rax
  int v34; // eax
  char *v35; // rcx
  InstanceConfigStoreManager *v36; // rax
  __int64 CurrentInstance; // rax
  __int64 v38; // rcx
  __int64 v39; // rbx
  __int64 v40; // rax
  signed int GlobalInstance; // eax
  signed int v42; // ebx
  struct __crt_locale_pointers *v43; // rax
  int v44; // eax
  char *v45; // rcx
  __int64 v46; // rbx
  __int64 v47; // rax
  struct IMemObj *v48; // rbx
  IOCompletionPortThreadPool *Instance; // rax
  IOCompletionPortThreadPool *v50; // rax
  signed int started; // eax
  signed int v52; // ebx
  struct __crt_locale_pointers *v53; // rax
  int v54; // eax
  char *v55; // rcx
  __int64 v56; // rcx
  RESOURCE *v57; // rbx
  __int64 ThreadLocalStoragePointer; // rdx
  unsigned __int64 v59; // rcx
  __int64 v60; // rsi
  __int64 *v61; // rdi
  volatile signed __int64 *v62; // r14
  LARGE_INTEGER v63; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v65; // r8
  LARGE_INTEGER v66; // rcx
  LONGLONG v67; // rax
  _QWORD *v68; // rcx
  __int64 v69; // rax
  volatile signed __int64 *v70; // rbx
  int v71; // r8d
  __int64 v72; // r8
  __int64 v73; // rax
  __int64 *v74; // rdi
  _QWORD *v75; // rdi
  __int64 v76; // rbx
  __int64 v77; // r14
  __int64 *v78; // rsi
  __int64 v79; // rbx
  __int64 v80; // rdi
  LARGE_INTEGER v81; // rbx
  signed __int64 v82; // r15
  __int64 v83; // r14
  __int64 v84; // r8
  __int64 v85; // rcx
  LARGE_INTEGER v86; // rcx
  LONGLONG v87; // rax
  __int64 *v88; // rcx
  unsigned __int64 v89; // rax
  SOS_ObjectStore *v90; // rcx
  unsigned int PoolIdForObject; // eax
  char v92; // r10
  __int64 v93; // r9
  __int64 v94; // rax
  _QWORD *v95; // r8
  __int64 v96; // rcx
  int v97; // r8d
  int v98; // r8d
  __int64 *v99; // rdi
  __int64 v100; // rbx
  __int64 v101; // rdx
  __int64 v102; // rcx
  __int64 v103; // rdx
  __int64 v104; // rcx
  bool v105; // al
  RESOURCE *v106; // rax
  struct IServerConfiguration *v107; // rcx
  struct IServerConfiguration *v108; // rdx
  __int64 v109; // rdx
  __int64 v110; // rcx
  signed int v111; // eax
  signed int v112; // ebx
  struct __crt_locale_pointers *v113; // rax
  int v114; // eax
  char *v115; // rcx
  char *v116; // rdi
  char v117; // r14
  bool v118; // si
  char v119; // bl
  void (**v120)(struct DBTABLE *, struct IMetadataAccess *, bool); // rbx
  struct IFTServiceMgr *FullTextServiceMgr; // rax
  __int64 v122; // rdx
  __int64 v123; // rcx
  __int64 v124; // rdx
  __int64 v125; // rcx
  __int64 v126; // rax
  const WCHAR *v127; // rax
  __int64 v128; // rax
  const WCHAR *v129; // rax
  __int64 v130; // rax
  int v131; // ebx
  const WCHAR *v132; // rax
  signed int LastError; // eax
  struct __crt_locale_pointers *v134; // rax
  int v135; // eax
  char *v136; // rcx
  __int64 v137; // rbx
  __int64 v138; // rax
  struct IMemObj *v139; // rdi
  signed int v140; // eax
  signed int v141; // ebx
  struct __crt_locale_pointers *v142; // rax
  int v143; // eax
  char *v144; // rcx
  int v145; // eax
  signed int v146; // ebx
  struct __crt_locale_pointers *v147; // rax
  int v148; // eax
  char *v149; // rcx
  int v150; // eax
  signed int v151; // ebx
  struct __crt_locale_pointers *v152; // rax
  int v153; // eax
  char *v154; // rcx
  __int64 v155; // rdx
  __int64 v156; // rcx
  __int64 v157; // rdx
  __int64 v158; // rcx
  DWORD v159; // eax
  unsigned int v160; // ebx
  char v161; // cl
  const wchar_t *v162; // rax
  int v163; // ebx
  __int64 v164; // rdx
  __int64 v165; // rcx
  int v166; // eax
  int v168; // [rsp+20h] [rbp-E0h]
  wchar_t *v169; // [rsp+28h] [rbp-D8h]
  wchar_t *v170; // [rsp+28h] [rbp-D8h]
  wchar_t *v171; // [rsp+28h] [rbp-D8h]
  int v173; // [rsp+50h] [rbp-B0h]
  unsigned int v174; // [rsp+54h] [rbp-ACh]
  DWORD flOldProtect; // [rsp+58h] [rbp-A8h] BYREF
  __int64 *v176; // [rsp+60h] [rbp-A0h]
  volatile signed __int32 *v177; // [rsp+68h] [rbp-98h] BYREF
  volatile signed __int64 *v178; // [rsp+70h] [rbp-90h]
  int v179; // [rsp+78h] [rbp-88h]
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp-80h] BYREF
  LARGE_INTEGER v181; // [rsp+88h] [rbp-78h] BYREF
  LARGE_INTEGER v182; // [rsp+90h] [rbp-70h] BYREF
  LARGE_INTEGER v183; // [rsp+98h] [rbp-68h] BYREF
  enum SOS_TIMERRESULT (__high *v184)(void *, unsigned int *, unsigned int *); // [rsp+A0h] [rbp-60h]
  enum SOS_TIMERRESULT (__high *v185)(void *); // [rsp+A8h] [rbp-58h]
  __int64 v186; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v187; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v188; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v189[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 *v190; // [rsp+D0h] [rbp-30h]
  char *v191; // [rsp+D8h] [rbp-28h]
  int v192; // [rsp+E0h] [rbp-20h]
  bool v193; // [rsp+E4h] [rbp-1Ch]
  __int128 v194; // [rsp+E5h] [rbp-1Bh] BYREF
  __int16 v195; // [rsp+F5h] [rbp-Bh]
  char v196; // [rsp+F7h] [rbp-9h]
  __int64 v197; // [rsp+F8h] [rbp-8h]
  BYTE v198[32]; // [rsp+100h] [rbp+0h] BYREF
  BYTE buf[4]; // [rsp+120h] [rbp+20h] BYREF
  int v200; // [rsp+124h] [rbp+24h]
  __int64 v201; // [rsp+128h] [rbp+28h]
  int v202; // [rsp+130h] [rbp+30h]
  BYTE v203[8]; // [rsp+138h] [rbp+38h] BYREF
  int v204; // [rsp+140h] [rbp+40h]
  char v205[512]; // [rsp+150h] [rbp+50h] BYREF
  char v206[512]; // [rsp+350h] [rbp+250h] BYREF
  char v207[512]; // [rsp+550h] [rbp+450h] BYREF
  char v208[512]; // [rsp+750h] [rbp+650h] BYREF
  char v209[512]; // [rsp+950h] [rbp+850h] BYREF
  char v210[512]; // [rsp+B50h] [rbp+A50h] BYREF
  char v211[512]; // [rsp+D50h] [rbp+C50h] BYREF
  char v212[512]; // [rsp+F50h] [rbp+E50h] BYREF
  char v213[512]; // [rsp+1150h] [rbp+1050h] BYREF
  wchar_t Buffer[264]; // [rsp+1350h] [rbp+1250h] BYREF
  wchar_t v215[264]; // [rsp+1560h] [rbp+1460h] BYREF

  v197 = -2;
  v5 = a4;
  v184 = a4;
  v6 = a3;
  v7 = a2;
  v173 = a2;
  v174 = a1;
  v8 = a5;
  v185 = a5;
  if ( *(_DWORD *)(GetXdbServerGlobals(a1, a2) + 11984)
    || (*(_BYTE *)(qword_10049F340 + 1072) & 0x40) != 0
    || (v9 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                       + SystemThread_TlsOffset)) != 0
    && (v10 = **(struct CSessionTraceFlags ***)(v9 + 56)) != 0
    && CSessionTraceFlags::CheckSessionTraceInternal(v10, 0x2186u) )
  {
    ReplicatedMasterDbId = GetReplicatedMasterDbId();
    SetMasterDbId(ReplicatedMasterDbId);
  }
  CaptureStartupPhaseTelemetry::CaptureStartupPhaseTelemetry((CaptureStartupPhaseTelemetry *)v198, 3);
  InitXE();
  XeSosCallbacks::InitializeXeSosCallbacks();
  v12 = *(ProcessConfig **)SOS_OS::GetClientProcessGlobals();
  IsEnabledCallbacks = (int (*const *)(void))XeSosCallbacks::GetXeSosIsEnabledCallbacks();
  ProcessConfig::SetXeSosIsEnabledCallbacks(v12, IsEnabledCallbacks);
  XeSosPublishCallbacks = (void (*const *)(void *))XeSosCallbacks::GetXeSosPublishCallbacks();
  ProcessConfig::SetXeSosPublishCallbacks(v12, XeSosPublishCallbacks);
  IsCollectEventColumnEnabledCallbacks = (int (*const *)(void))XeSosCallbacks::GetXeSosIsCollectEventColumnEnabledCallbacks();
  ProcessConfig::SetXeSosIsCollectEventColumnEnabledCallbacks(v12, IsCollectEventColumnEnabledCallbacks);
  v16 = SvlSystemBoot();
  v17 = v16;
  if ( v16 < 0 )
  {
    _mm_lfence();
    SetWin32ExitCode(v16);
    DefaultLocale = GetDefaultLocale();
    v19 = StringCchPrintf_lA(
            v205,
            0x200u,
            "%hs (HRESULT 0x%x)",
            DefaultLocale,
            "SVL library post-boot initialization",
            v17);
    v20 = "SVL library post-boot initialization";
    if ( v19 >= 0 )
      v20 = v205;
    FailAndExit(v20);
  }
  *((_DWORD *)qword_10049F360 + 3631) = 0;
  if ( (v7 & 1) == 0 )
    goto LABEL_16;
  v21 = qword_10049F360;
  if ( (*((_DWORD *)qword_10049F360 + 12127) & 0x2000) != 0 )
  {
LABEL_17:
    *((_DWORD *)v21 + 3631) = 1;
    goto LABEL_18;
  }
  if ( !*((_DWORD *)qword_10049F360 + 3626) )
    goto LABEL_19;
  if ( (unsigned __int8)HostReg_IsFeatureSwitchOn(L"SQL.Config", L"ReducedFootprintForLogicalMaster", 0)
    && IsLogicalMaster() )
  {
LABEL_16:
    v21 = qword_10049F360;
    goto LABEL_17;
  }
LABEL_18:
  v21 = qword_10049F360;
LABEL_19:
  v22 = v7 & 0x8000;
  if ( (v7 & 0x8000) == 0 )
    InitXeForSqlLang(*((_DWORD *)v21 + 3626) != 0);
  InitAdhocXESessionSupport();
  InitXeForSqlmin();
  InitXeForQds(*((_DWORD *)qword_10049F360 + 3626) != 0);
  CaptureStartupPhaseTelemetry::~CaptureStartupPhaseTelemetry((CaptureStartupPhaseTelemetry *)v198);
  v23 = qword_10049F360;
  if ( *((_DWORD *)qword_10049F360 + 3628) )
  {
    ServiceFabricInit();
    v23 = qword_10049F360;
  }
  if ( *((_DWORD *)v23 + 3626) )
    HadrFabricInit();
  IServerConfiguration::SubscribeAndGetDynamicStringSetting(
    s_pServerConf,
    L"SQL",
    L"BaseTraceFlags",
    (void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *))TraceFlagUpdateCallback,
    qword_1004D28E0,
    0);
  IServerConfiguration::SubscribeAndGetDynamicStringSetting(
    s_pServerConf,
    L"SQL",
    L"TraceFlags",
    (void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *))TraceFlagUpdateCallback,
    qword_1004D3060,
    0);
  CFeatureSwitchesDk::Init(1);
  CFeatureSwitchesTsEs::Init(1);
  CFeatureSwitchesMin::Init(1);
  CFeatureSwitchesTds::Init(1);
  CFeatureSwitchesQds::Init(1);
  CFeatureSwitchesLangSvc::Init(1);
  CFeatureSwitchesFido::Init(1);
  CFeatureSwitchesBluemoon::Init(1);
  v24 = (const struct CFeatureSwitchesQds *)CFeatureSwitchesQds::ExportCurrentInstance();
  v25 = (const struct CFeatureSwitchesMin *)CFeatureSwitchesMin::ExportCurrentInstance();
  SQLLangImportFeatureSwitches(v25, v24);
  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    CFeatureSwitchesFabric::Init(1);
    v28 = CFeatureSwitchesLangSvc::ExportCurrentInstance();
    v29 = CFeatureSwitchesMin::ExportCurrentInstance();
    HadrFabricImportFeatureSwitches(v29, v28);
  }
  if ( *((_DWORD *)qword_10049F360 + 3626)
    && (*(_BYTE *)(((__int64 (*)(void))CFeatureSwitchesMin::GetCurrentInstance)() + 693)
     || *(_BYTE *)(CFeatureSwitchesLangSvc::GetCurrentInstance() + 909)) )
  {
    InstanceConfigStoreManager = (InstanceConfigStoreManager *)InstanceConfigStoreManager::GetInstanceConfigStoreManager();
    v31 = InstanceConfigStoreManager::PostInit(InstanceConfigStoreManager);
    v32 = v31;
    if ( v31 < 0 )
    {
      _mm_lfence();
      SetWin32ExitCode(v31);
      v33 = GetDefaultLocale();
      LODWORD(v169) = v32;
      v34 = StringCchPrintf_lA(
              v206,
              0x200u,
              "%hs (HRESULT 0x%x)",
              v33,
              "Instance Config Store Manager post initialization failed.",
              v169);
      v35 = "Instance Config Store Manager post initialization failed.";
      if ( v34 >= 0 )
        v35 = v206;
      FailAndExit(v35);
    }
    v36 = (InstanceConfigStoreManager *)InstanceConfigStoreManager::GetInstanceConfigStoreManager();
    InstanceConfigStoreManager::ParsePropertyBag(v36);
  }
  if ( *((_DWORD *)qword_10049F360 + 3626)
    && *(_DWORD *)(GetXdbServerGlobals(v27, v26) + 12000)
    && (int)LoadCertificateAndAddToStore(L"c:\\cert\\fabricClientCert.pfx", 0) < 0 )
  {
    LogSystemMetadataNotSentToClient(L"%ls", L"Certificate load for SQLPAL failed.\n");
  }
  InitXdbSrvGlobals(v27, v26);
  LOBYTE(v168) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"XEvent",
    L"MaxRetry",
    &dword_1004A0A18,
    v168,
    0);
  if ( (*(_BYTE *)(((__int64 (*)(void))CFeatureSwitchesMin::GetCurrentInstance)() + 1260)
     || (*(_BYTE *)(qword_10049F340 + 1423) & 8) != 0)
    && (*(_BYTE *)(qword_10049F340 + 1423) & 0x10) == 0
    || ((CurrentInstance = CFeatureSwitchesMin::GetCurrentInstance(qword_10049F340),
         v38 = qword_10049F340,
         *(_BYTE *)(CurrentInstance + 1249))
     || *(char *)(qword_10049F340 + 1675) < 0)
    && (*(_BYTE *)(qword_10049F340 + 1676) & 1) == 0 )
  {
    CGlobalTraceFlags::TurnOn(11386, 0);
    CGlobalTraceFlags::TurnOn(11392, 0);
    v38 = qword_10049F340;
  }
  if ( (*(_BYTE *)(v38 + 1423) & 4) != 0 )
  {
    v39 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v40 = *(_QWORD *)(v39 + 256);
    if ( !v40 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v40 = *(_QWORD *)(v39 + 256);
    }
    GlobalInstance = IOCompletionPortThreadPool::CreateGlobalInstance(*(struct IMemObj **)(*(_QWORD *)(v40 + 992) + 320LL));
    v42 = GlobalInstance;
    if ( GlobalInstance < 0 )
    {
      _mm_lfence();
      SetWin32ExitCode(GlobalInstance);
      v43 = GetDefaultLocale();
      LODWORD(v170) = v42;
      v44 = StringCchPrintf_lA(
              v207,
              0x200u,
              "%hs (HRESULT 0x%x)",
              v43,
              "Failed to initialize IOCompletionPortThreadPool",
              v170);
      v45 = "Failed to initialize IOCompletionPortThreadPool";
      if ( v44 >= 0 )
        v45 = v207;
      FailAndExit(v45);
    }
    v46 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v47 = *(_QWORD *)(v46 + 256);
    if ( !v47 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v47 = *(_QWORD *)(v46 + 256);
    }
    v48 = *(struct IMemObj **)(*(_QWORD *)(v47 + 992) + 320LL);
    Instance = (IOCompletionPortThreadPool *)IOCompletionPortThreadPool::GetInstance();
    IOCompletionPortThreadPool::SetParameters(Instance, v48, SOS_PublicGlobals::sm_cpuCountAtStartup, 0);
    v50 = (IOCompletionPortThreadPool *)IOCompletionPortThreadPool::GetInstance();
    started = IOCompletionPortThreadPool::StartCompletionPorts(v50);
    v52 = started;
    if ( started < 0 )
    {
      _mm_lfence();
      SetWin32ExitCode(started);
      v53 = GetDefaultLocale();
      LODWORD(v170) = v52;
      v54 = StringCchPrintf_lA(
              v208,
              0x200u,
              "%hs (HRESULT 0x%x)",
              v53,
              "Failed to start completion ports threads",
              v170);
      v55 = "Failed to start completion ports threads";
      if ( v54 >= 0 )
        v55 = v208;
      FailAndExit(v55);
    }
    StartupDependencies::SetAsCompleted(20);
    log_unlocalized_systemmetadata(
      L"%hs - IOCompletionPortThreadPool successfully started with %u threads.",
      "InitServerComponents",
      SOS_PublicGlobals::sm_cpuCountAtStartup);
  }
  if ( *(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance(v38) + 1577) )
  {
    LOBYTE(v56) = 1;
    ConnectFileShare(v56);
  }
  v57 = qword_10049F360;
  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    if ( *(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance(v56) + 402) )
    {
      v60 = 0;
      v177 = 0;
      if ( (unsigned int)SOS_OS::EnqueueTask(ActivateCodePackage, 0, 0, &v177, -1) )
      {
        scierrlog(0x42E0u, L"InitServerComponents");
        SQLExit(44, 0, 2147942414LL);
      }
      else
      {
        v61 = (__int64 *)v177;
        if ( _InterlockedExchangeAdd(v177 + 10, 0xFFFFFFFF) == 1 )
        {
          if ( v61[3] )
          {
            TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v61 + 2);
          }
          else
          {
            if ( *((_DWORD *)v61 + 46) == 2 )
            {
              v178 = (volatile signed __int64 *)(v61[20] + 4952);
              v62 = v178;
              v179 = 0;
              v63.QuadPart = 0;
              UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
              if ( *(_DWORD *)v178 || _InterlockedCompareExchange64(v178, UniqueThread_low, 0) )
              {
                if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                {
                  v65 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                      + SystemThread_TlsOffset;
                  if ( v65 && *(_QWORD *)(v65 + 272) == v65 )
                    v60 = *(_QWORD *)(v65 + 256);
                  if ( v60 )
                  {
                    if ( Base_PublicGlobals::sm_invariantTscAvailable )
                    {
                      QueryPerformanceCounter(&PerformanceCount);
                      v63 = PerformanceCount;
                    }
                    else
                    {
                      v63.QuadPart = MEMORY[0x7FFE0008];
                    }
                  }
                }
                if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                  Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v62, UniqueThread_low);
                else
                  Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v62, v60, UniqueThread_low);
                if ( v60 )
                {
                  if ( Base_PublicGlobals::sm_invariantTscAvailable )
                  {
                    QueryPerformanceCounter(&v181);
                    v66 = v181;
                  }
                  else
                  {
                    v66.QuadPart = MEMORY[0x7FFE0008];
                  }
                  v67 = 0;
                  if ( v66.QuadPart >= (unsigned __int64)v63.QuadPart )
                    v67 = v66.QuadPart - v63.QuadPart;
                  *(_QWORD *)(v60 + 3192) += v67;
                }
              }
              v179 = 1;
              v68 = (_QWORD *)v61[1];
              v69 = *v61;
              *(_QWORD *)(v69 + 8) = v68;
              *v68 = v69;
              v61[1] = 0;
              *v61 = 0;
              v70 = v178;
              if ( v178 )
              {
                if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                {
                  v71 = rand();
                  if ( v71 == 5 * (v71 / 5) )
                    Spinlock<11,2,268435714>::UpdateStatSnapshot();
                }
                *v70 = 0;
                v178 = 0;
                v179 = 0;
              }
            }
            ThreadLocalStoragePointer = (__int64)NtCurrentTeb()->ThreadLocalStoragePointer;
            v59 = SystemThread_TlsIndex;
            v72 = *(_QWORD *)(ThreadLocalStoragePointer + 8LL * SystemThread_TlsIndex) + SystemThread_TlsOffset;
            if ( v72
              && *(_QWORD *)(v72 + 272) == v72
              && (v73 = *(_QWORD *)(v72 + 256)) != 0
              && *(__int64 **)(v73 + 528) == v61 )
            {
              if ( v61 )
                v74 = v61 - 1;
              else
                v74 = 0;
              *v74 = (__int64)&ISOSHost_TaskImpl::`vftable';
              v75 = v74 + 1;
              v76 = v75[22];
              if ( v76 )
              {
                if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
                {
                  _InterlockedDecrement((volatile signed __int32 *)(v76 + 112));
                  v76 = v75[22];
                }
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v76 + 24), 0xFFFFFFFF) == 1 )
                {
                  if ( *(_QWORD *)(v76 + 8) )
                    TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v76 + 16), v76);
                  SOSHost::Destroy((SOSHost *)v76);
                }
              }
            }
            else
            {
              v59 = v61[21];
              if ( v59 && *(_QWORD *)(v59 + 240) && !SOS_Node::IsTaskStoreDisabled((SOS_Node *)v59) )
              {
                v77 = *(_QWORD *)(v61[21] + 240);
                v78 = v61 - 1;
                *(v61 - 1) = (__int64)&ISOSHost_TaskImpl::`vftable';
                v176 = v61;
                v79 = v61[22];
                if ( v79 )
                {
                  if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
                  {
                    _InterlockedDecrement((volatile signed __int32 *)(v79 + 112));
                    v79 = v61[22];
                  }
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v79 + 24), 0xFFFFFFFF) == 1 )
                  {
                    if ( *(_QWORD *)(v79 + 8) )
                      TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v79 + 16), v79);
                    SOSHost::Destroy((SOSHost *)v79);
                  }
                }
                v80 = *(_QWORD *)(v77 + 2016);
                v81.QuadPart = 0;
                v82 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
                if ( *(_DWORD *)(v80 + 40)
                  || _InterlockedCompareExchange64((volatile signed __int64 *)(v80 + 40), v82, 0) )
                {
                  v83 = 0;
                  if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
                  {
                    v84 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                        + SystemThread_TlsOffset;
                    if ( v84 && *(_QWORD *)(v84 + 272) == v84 )
                      v83 = *(_QWORD *)(v84 + 256);
                    if ( v83 )
                    {
                      if ( Base_PublicGlobals::sm_invariantTscAvailable )
                      {
                        QueryPerformanceCounter(&v182);
                        v81 = v182;
                      }
                      else
                      {
                        v81.QuadPart = MEMORY[0x7FFE0008];
                      }
                    }
                  }
                  v85 = v80 + 40;
                  if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                    Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v85, v82);
                  else
                    Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v85, v83, v82);
                  if ( v83 )
                  {
                    if ( Base_PublicGlobals::sm_invariantTscAvailable )
                    {
                      QueryPerformanceCounter(&v183);
                      v86 = v183;
                    }
                    else
                    {
                      v86.QuadPart = MEMORY[0x7FFE0008];
                    }
                    ThreadLocalStoragePointer = v86.QuadPart - v81.QuadPart;
                    v87 = 0;
                    if ( v86.QuadPart >= (unsigned __int64)v81.QuadPart )
                      v87 = v86.QuadPart - v81.QuadPart;
                    *(_QWORD *)(v83 + 3192) += v87;
                  }
                }
                if ( *(_QWORD *)(v80 + 8) >= *(_QWORD *)v80 )
                {
                  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                  {
                    v98 = rand();
                    if ( v98 == 5 * (v98 / 5) )
                      Spinlock<34,1,268435714>::UpdateStatSnapshot();
                  }
                  *(_QWORD *)(v80 + 40) = 0;
                  (*(void (__fastcall **)(__int64 *))(v80 + 48))(v78);
                  v6 = a3;
                }
                else
                {
                  if ( *(_BYTE *)(*(_QWORD *)(v80 + 32) + 5820LL) )
                  {
                    v88 = (__int64 *)(v80 + 16 * ((*(_DWORD *)(v80 + 1176) & 0x3F) + 9LL));
                    *v78 = *v88;
                    if ( !*v88 )
                      v88[1] = (__int64)v78;
                    *v88 = (__int64)v78;
                    ++*(_QWORD *)(v80 + 1176);
                    VirtualProtect(v78, 0x1000u, 1u, &flOldProtect);
                  }
                  else
                  {
                    *v78 = *(_QWORD *)(v80 + 128);
                    if ( !*(_QWORD *)(v80 + 128) )
                      *(_QWORD *)(v80 + 136) = v78;
                    *(_QWORD *)(v80 + 128) = v78;
                  }
                  v89 = *(_QWORD *)(v80 + 1168) + 1LL;
                  ++*(_QWORD *)(v80 + 8);
                  v90 = *(SOS_ObjectStore **)(v80 + 32);
                  if ( !*((_BYTE *)v90 + 5820) && v89 >= 0x20 )
                  {
                    PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v90, (struct SList *)v78);
                    v92 = PoolIdForObject;
                    v93 = v80 + 8LL * PoolIdForObject;
                    v94 = *(_QWORD *)(v80 + 128);
                    v95 = *(_QWORD **)(v80 + 136);
                    if ( v95 != (_QWORD *)(v80 + 128) && v95 )
                    {
                      *v95 = *(_QWORD *)(v93 + 1184);
                      *(_QWORD *)(v93 + 1184) = v94;
                    }
                    *(_QWORD *)(v80 + 128) = 0;
                    *(_QWORD *)(v80 + 136) = v80 + 128;
                    v89 = 0;
                    ThreadLocalStoragePointer = 1LL << v92;
                    v96 = *(_QWORD *)(v80 + 1696);
                    if ( ((1LL << v92) & v96) == 0 )
                    {
                      ThreadLocalStoragePointer |= v96;
                      *(_QWORD *)(v80 + 1696) = ThreadLocalStoragePointer;
                    }
                  }
                  *(_QWORD *)(v80 + 1168) = v89;
                  v59 = *(_QWORD *)&SOS_PublicGlobals::sm_SpinlockStatSnapshot;
                  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
                  {
                    v97 = rand();
                    ThreadLocalStoragePointer = (unsigned int)(v97 / 5);
                    v59 = (unsigned int)(5 * ThreadLocalStoragePointer);
                    if ( v97 == (_DWORD)v59 )
                      Spinlock<34,1,268435714>::UpdateStatSnapshot();
                  }
                  *(_QWORD *)(v80 + 40) = 0;
                  v6 = a3;
                }
              }
              else
              {
                v99 = v61 - 1;
                if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
                {
                  VirtualFree(v99, 0, 0x8000u);
                }
                else
                {
                  v176 = v99;
                  if ( v99 )
                  {
                    *v99 = (__int64)&ISOSHost_TaskImpl::`vftable';
                    v176 = v99 + 1;
                    v100 = v99[23];
                    if ( v100 )
                    {
                      if ( (SOS_PublicGlobals::sm_osStats & 8) != 0 )
                      {
                        _InterlockedDecrement((volatile signed __int32 *)(v100 + 112));
                        v100 = v99[23];
                      }
                      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v100 + 24), 0xFFFFFFFF) == 1 )
                      {
                        if ( *(_QWORD *)(v100 + 8) )
                          TList<HostManager,SOSHost,0,TListSLock>::RemoveElem(*(_QWORD *)(v100 + 16), v100);
                        SOSHost::Destroy((SOSHost *)v100);
                      }
                    }
                    operator delete(v99, 0x3E0u);
                  }
                }
              }
            }
          }
        }
      }
    }
    v105 = *(_DWORD *)(GetXdbServerGlobals(v59, ThreadLocalStoragePointer) + 8308)
        || *(_DWORD *)(GetXdbServerGlobals(v102, v101) + 11976) && *(_DWORD *)(GetXdbServerGlobals(v104, v103) + 11996);
    byte_1004A0B11 = v105;
    v57 = qword_10049F360;
    v7 = v173;
    v5 = v184;
    v8 = v185;
  }
  *((_DWORD *)v57 + 3630) = IsHekatonEnabled();
  v106 = qword_10049F360;
  if ( *((_DWORD *)qword_10049F360 + 3630)
    || (v107 = s_pServerConf, v108 = s_pServerConf, *((_BYTE *)s_pServerConf + 17))
    && !*((_DWORD *)qword_10049F360 + 13)
    && !*((_DWORD *)qword_10049F360 + 3631)
    && !*((_DWORD *)qword_10049F360 + 3645)
    && (!*(_DWORD *)(GetXdbServerGlobals(s_pServerConf, s_pServerConf) + 13060)
     || (v106 = qword_10049F360, !*((_DWORD *)qword_10049F360 + 3626))) )
  {
    InitHekatonXEPackages();
    v106 = qword_10049F360;
  }
  if ( (*((_BYTE *)v106 + 48500) & 1) != 0
    || !*((_DWORD *)v106 + 3626) && *(_BYTE *)(GetXdbServerGlobals(v107, v108) + 12004)
    || *(_BYTE *)(GetXdbServerGlobals(v107, v108) + 12004) )
  {
    if ( *(_BYTE *)(CFeatureSwitchesMin::ExportCurrentInstance() + 541) || (*(_BYTE *)(qword_10049F340 + 1425) & 4) != 0 )
      *((_DWORD *)qword_10049F360 + 12125) |= 4u;
    if ( *(_BYTE *)(CFeatureSwitchesMin::ExportCurrentInstance() + 542)
      || (*(_BYTE *)(qword_10049F340 + 1425) & 2) != 0
      || !*(_BYTE *)(CFeatureSwitchesMin::ExportCurrentInstance() + 112)
      && (*(_BYTE *)(qword_10049F340 + 1262) & 0x20) == 0 )
    {
      *((_DWORD *)qword_10049F360 + 12125) |= 2u;
    }
  }
  if ( *(_BYTE *)(GetXdbServerGlobals(v110, v109) + 12004) )
  {
    v111 = StartFidoGLMManager();
    v112 = v111;
    if ( v111 < 0 )
    {
      _mm_lfence();
      SetWin32ExitCode(v111);
      v113 = GetDefaultLocale();
      LODWORD(v170) = v112;
      v114 = StringCchPrintf_lA(v209, 0x200u, "%hs (HRESULT 0x%x)", v113, "Fido Initialization failure", v170);
      v115 = "Fido Initialization failure";
      if ( v114 >= 0 )
        v115 = v209;
      FailAndExit(v115);
    }
  }
  if ( *((_BYTE *)qword_10049F360 + 48768) )
  {
    InitBdcRootCA();
    InitBdcControllerClientCert();
  }
  if ( OsInfo::IsLinux(SOS_OS_OsInfo) )
    InstallClientTLSCertificatesLinux();
  InitLedgerAlg();
  SimdHelpers::OutputCpuInstructionSupport(SOS_PublicGlobals::sm_cpuInstructionSupport);
  if ( FUseReplicatedServerContext() )
    v116 = (char *)qword_10049F360 + 28520;
  else
    v116 = (char *)qword_10049F360 + 14864;
  if ( !v5 )
    v5 = (enum SOS_TIMERRESULT (__high *)(void *, unsigned int *, unsigned int *))SystemTaskEntryPoint;
  if ( !v8 )
    v8 = (enum SOS_TIMERRESULT (__high *)(void *))SystemTaskInit;
  SetOnDemandTaskCallBacks(v5, v8);
  v117 = 0;
  v118 = 0;
  if ( !v22 )
  {
    SetupOdsCallbacks((struct ods_callbacks *)&x_odsCallbacks);
    ODS_init(&x_odsCallbacks);
    v117 = 1;
    v119 = *(_BYTE *)(CFeatureSwitchesQds::ExportCurrentInstance() + 119);
    v118 = v119 == 0;
    v194 = 0;
    v195 = 0;
    v196 = 0;
    v189[0] = *((_DWORD *)v116 + 3093);
    v189[1] = *((_DWORD *)v116 + 3116);
    if ( dword_1004D4888 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
    {
      Init_thread_header(&dword_1004D4888);
      if ( dword_1004D4888 == -1 )
      {
        qword_1004D4890 = (__int64)WaitReadyToAcceptConnections;
        qword_1004D4898 = (__int64)ShutdownComponents;
        qword_1004D48A0 = (__int64)ConfigureSecurityForStartup;
        Init_thread_footer(&dword_1004D4888);
      }
    }
    v190 = &qword_1004D4890;
    v191 = (char *)qword_10049F360 + 14848;
    v192 = v7;
    v193 = v119 == 0;
    if ( *((_DWORD *)qword_10049F360 + 3626) )
    {
      SqlFabricGetDumpHooks((char *)&v194 + 3, (char *)&v194 + 11);
      InitPmoForFabricProperties();
    }
    SQLLangInitComponents((const struct SQLLangInitBlock *)v189);
  }
  v120 = &off_1004A0A20;
  if ( v6 )
    v120 = v6;
  if ( v117 && !v118 )
    InitializeQdsIntrinsics();
  FullTextServiceMgr = GetFullTextServiceMgr();
  SQLMinInitComponents(
    *((unsigned int *)v116 + 3116),
    FullTextServiceMgr,
    v120,
    v174,
    v7,
    failpoint_list_file,
    off_1004A0AD8);
  if ( v117 && !v118 )
    InitializeQDSComponent();
  MemoryNode::RecalculateTarget();
  if ( *(_DWORD *)(GetXdbServerGlobals(v123, v122) + 8308) )
    InitializeSFWLists();
  InitSUM();
  if ( !*((_DWORD *)qword_10049F360 + 3626)
    || (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) != 2
    && (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) != 3 )
  {
    goto LABEL_264;
  }
  v126 = XDBWinFabGlobals::Get();
  v127 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v126 + 24) + 216LL))(*(_QWORD *)(v126 + 24));
  if ( !SetEnvironmentVariableW(L"Fabric_ApplicationTypeName", v127)
    || (v128 = XDBWinFabGlobals::Get(),
        v129 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v128 + 24) + 40LL))(*(_QWORD *)(v128 + 24)),
        !SetEnvironmentVariableW(L"Fabric_CodePackageVersion", v129))
    || (v130 = XDBWinFabGlobals::Get(),
        v131 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(v130 + 24) + 224LL))(
                 *(_QWORD *)(v130 + 24),
                 &v186),
        v131 >= 0)
    && v186
    && (v132 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v186 + 24LL))(v186),
        !SetEnvironmentVariableW(L"Fabric_ServiceManifestName", v132)) )
  {
    LastError = GetLastError();
    v131 = LastError;
    if ( LastError > 0 )
      v131 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( v131 < 0 )
  {
    _mm_lfence();
    SetWin32ExitCode(v131);
    v134 = GetDefaultLocale();
    LODWORD(v171) = v131;
    v135 = StringCchPrintf_lA(
             v210,
             0x200u,
             "%hs (HRESULT 0x%x)",
             v134,
             "StoreActivationContextEnvVariables failed.",
             v171);
    v136 = "StoreActivationContextEnvVariables failed.";
    if ( v135 >= 0 )
      v136 = v210;
    FailAndExit(v136);
  }
  v137 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v138 = *(_QWORD *)(v137 + 256);
  if ( !v138 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v138 = *(_QWORD *)(v137 + 256);
  }
  v139 = *(struct IMemObj **)(*(_QWORD *)(v138 + 992) + 320LL);
  v140 = LaunchContainerShareUtilProcess(v139);
  v141 = v140;
  if ( v140 < 0 )
  {
    _mm_lfence();
    SetWin32ExitCode(v140);
    v142 = GetDefaultLocale();
    LODWORD(v171) = v141;
    v143 = StringCchPrintf_lA(v211, 0x200u, "%hs (HRESULT 0x%x)", v142, "LaunchContainerShareUtilProcess failed.", v171);
    v144 = "LaunchContainerShareUtilProcess failed.";
    if ( v143 >= 0 )
      v144 = v211;
    FailAndExit(v144);
  }
  HostReg_GetCodePackageDirectory(&v187);
  v145 = StringCchPrintfW(Buffer, 0x105u, L"%s\\%s", v187, L"SqlAgent\\sqlagent.exe");
  v146 = v145;
  if ( v145 < 0 )
  {
    _mm_lfence();
    log_unlocalized(
      L"[%hs] ERROR: StringCchPrintfW of message failed. (HRESULT 0x%x)",
      "LaunchWcowSidecarProcess",
      (unsigned int)v145);
LABEL_255:
    _mm_lfence();
    SetWin32ExitCode(v146);
    v147 = GetDefaultLocale();
    LODWORD(v171) = v146;
    v148 = StringCchPrintf_lA(
             v212,
             0x200u,
             "%hs (HRESULT 0x%x)",
             v147,
             "LaunchWcowSidecarProcess for SqlAgent failed.",
             v171);
    v149 = "LaunchWcowSidecarProcess for SqlAgent failed.";
    if ( v148 >= 0 )
      v149 = v212;
    FailAndExit(v149);
    goto LABEL_258;
  }
  v146 = BootAndKeepProcessAliveInWcow(Buffer, L"sqlagent.exe -c -xdb -wcowchild", L"SqlAgent", v139);
  if ( v146 < 0 )
    goto LABEL_255;
LABEL_258:
  HostReg_GetCodePackageDirectory(&v188);
  v150 = StringCchPrintfW(v215, 0x105u, L"%s\\%s", v188, L"sqlservr\\binn\\fdHost.exe");
  v151 = v150;
  if ( v150 >= 0 )
  {
    v151 = BootAndKeepProcessAliveInWcow(v215, L"fdHost.exe -wcow", L"FdHost", v139);
    if ( v151 >= 0 )
      goto LABEL_264;
  }
  else
  {
    _mm_lfence();
    log_unlocalized(
      L"[%hs] ERROR: StringCchPrintfW of message failed. (HRESULT 0x%x)",
      "LaunchWcowSidecarProcess",
      (unsigned int)v150);
  }
  _mm_lfence();
  SetWin32ExitCode(v151);
  v152 = GetDefaultLocale();
  LODWORD(v171) = v151;
  v153 = StringCchPrintf_lA(
           v213,
           0x200u,
           "%hs (HRESULT 0x%x)",
           v152,
           "LaunchWcowSidecarProcess for FdHost failed.",
           v171);
  v154 = "LaunchWcowSidecarProcess for FdHost failed.";
  if ( v153 >= 0 )
    v154 = v213;
  FailAndExit(v154);
LABEL_264:
  if ( *(_DWORD *)(GetXdbServerGlobals(v125, v124) + 11976) && *(_DWORD *)(GetXdbServerGlobals(v156, v155) + 12000) )
    BootSqlAgent();
  if ( !*((_DWORD *)qword_10049F360 + 3626) || !*(_DWORD *)(GetXdbServerGlobals(v156, v155) + 12000) )
  {
    if ( OsInfo::IsXPlatInstance(SOS_OS_OsInfo)
      && (unsigned int)SOS_OS::EnqueueTask(EntryPointCrossPlatTask, off_1004A3368, 130, &g_taskInitSqlAgentUser, -1) )
    {
      scierrlog(0xB0A5u, 2147942414LL);
      SQLExit(153, 0, 2147942414LL);
    }
    if ( OsInfo::IsXPlatInstance(SOS_OS_OsInfo) )
    {
      v201 = 0;
      *(_DWORD *)buf = 8;
      v200 = 7776000;
      v202 = 1;
      v159 = NetUserModalsSet(0, 0, buf, 0);
      v160 = 0;
      if ( v159 || (v160 = 1, *(_QWORD *)v203 = 0, v204 = 0, (v159 = NetUserModalsSet(0, 3u, v203, 0)) != 0) )
      {
        scierrlog(0x812Au, v159, v160);
        SQLExit(379);
      }
    }
    if ( OsInfo::IsXPlatInstance(SOS_OS_OsInfo) )
    {
      if ( dword_1004D48C4 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
      {
        Init_thread_header(&dword_1004D48C4);
        if ( dword_1004D48C4 == -1 )
        {
          qword_1004A33B0 = (__int64)L"set deadlock_priority 10\n"
                                      "DECLARE @cmd1 nvarchar(max)\n"
                                      "\n"
                                      "IF NOT EXISTS (SELECT * FROM sys.server_principals WHERE name = N'NT AUTHORITY\\SY"
                                      "STEM')\n"
                                      "BEGIN\n"
                                      "\tSELECT @cmd1 = 'CREATE LOGIN [NT AUTHORITY\\SYSTEM] FROM WINDOWS'\n"
                                      "\tEXEC (@cmd1)\n"
                                      "\n"
                                      "\tEXEC sys.sp_dropsrvrolemember N'NT AUTHORITY\\SYSTEM', N'sysadmin'\n"
                                      "END\n";
          xmmword_1004A33B8 = 0;
          Init_thread_footer(&dword_1004D48C4);
        }
      }
      *(_QWORD *)&xmmword_1004A33B8 = L"set deadlock_priority 10\n"
                                       "DECLARE @cmd1 nvarchar(max)\n"
                                       "\n"
                                       "\tSELECT @cmd1 = 'GRANT VIEW SERVER STATE TO [NT AUTHORITY\\SYSTEM]'\n"
                                       "\tEXEC (@cmd1)\n"
                                       "\n"
                                       "\tSELECT @cmd1 = 'GRANT CONNECT ANY DATABASE TO [NT AUTHORITY\\SYSTEM]'\n"
                                       "\tEXEC (@cmd1)\n"
                                       "\n"
                                       "\tSELECT @cmd1 = 'GRANT VIEW ANY DEFINITION TO [NT AUTHORITY\\SYSTEM]'\n"
                                       "\tEXEC (@cmd1)\n"
                                       "\n"
                                       "\tSELECT @cmd1 = 'GRANT ALTER ANY EVENT SESSION TO [NT AUTHORITY\\SYSTEM]'\n"
                                       "\tEXEC (@cmd1)\n";
      v161 = *((_BYTE *)qword_10049F360 + 48784);
      v162 = L"set deadlock_priority 10\n"
              "DECLARE @cmd1 nvarchar(max)\n"
              "\n"
              "\tSELECT @cmd1 = 'GRANT VIEW SERVER STATE TO [NT AUTHORITY\\SYSTEM]'\n"
              "\tEXEC (@cmd1)\n"
              "\n"
              "\tSELECT @cmd1 = 'GRANT CONNECT SQL TO [NT AUTHORITY\\SYSTEM]'\n"
              "\tEXEC (@cmd1)\n"
              "\n"
              "\tSELECT @cmd1 = 'GRANT ALTER ANY AVAILABILITY GROUP TO [NT AUTHORITY\\SYSTEM]'\n"
              "\tEXEC (@cmd1)\n";
      if ( !v161 )
        v162 = (const wchar_t *)*((_QWORD *)&xmmword_1004A33B8 + 1);
      *((_QWORD *)&xmmword_1004A33B8 + 1) = v162;
      v163 = (v161 != 0) + 2;
      if ( dword_1004D48C8 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
      {
        Init_thread_header(&dword_1004D48C8);
        if ( dword_1004D48C8 == -1 )
        {
          dword_1004A33A0 = v163;
          dword_1004A33A4 = 49931;
          qword_1004A33A8 = 0;
          Init_thread_footer(&dword_1004D48C8);
        }
      }
      if ( (unsigned int)SOS_OS::EnqueueTask(
                           EntryPointCrossPlatTask,
                           &off_1004A3390,
                           130,
                           &g_taskInitCrossPlatTelemetryAndClustering,
                           -1) )
      {
        scierrlog(0x42E0u, L"InitCrossPlatTelemetryAndClustering");
        SQLExit(152, 0, 2147942414LL);
      }
    }
  }
  if ( *((_DWORD *)qword_10049F360 + 3626)
    && ((*(_BYTE *)(GetXdbServerGlobals(v158, v157) + 12009) || *(_BYTE *)(GetXdbServerGlobals(v165, v164) + 12008))
     && !*(_BYTE *)(GetXdbServerGlobals(v165, v164) + 12004)
     || *(_BYTE *)(GetXdbServerGlobals(v165, v164) + 12004)) )
  {
    if ( *(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance(v165) + 1585) )
    {
      v166 = RESOURCE::ParseRgInstanceLevelSloPropertyBag(qword_10049F360);
      if ( v166 < 0 )
      {
        _mm_lfence();
        log_unlocalized_systemmetadata(
          L"%hs - DW FIDO SloPropertyBag read and apply failed with hr = 0x%x .",
          "InitServerComponents",
          (unsigned int)v166);
      }
    }
  }
  if ( *((_DWORD *)qword_10049F360 + 3626)
    && (*((_BYTE *)&SOS_PublicGlobals::sm_traceFlags + 199) & 8) == 0
    && s_pServerConf
    && !IServerConfiguration::SubscribeAndGetDynamicStringSetting(
          s_pServerConf,
          L"SQL",
          L"ExcludeFromDumpClerkTypeString",
          ClerkConfig::ExcludeFromDumpClerkTypeStringCallBack,
          0,
          0) )
  {
    log_unlocalized_systemmetadata(L"Failed to read ExcludeFromDumpClerkTypeString setting.");
  }
  return EventManualInternal<SuspendQueueSLock>::Signal(&off_1004A09E8, 0);
}

```

## disassembly

```asm
0x100412470  push    rbp
0x100412472  push    rbx
0x100412473  push    rsi
0x100412474  push    rdi
0x100412475  push    r12
0x100412477  push    r13
0x100412479  push    r14
0x10041247b  push    r15
0x10041247d  lea     rbp, [rsp-1688h]
0x100412485  mov     eax, 1788h
0x10041248a  call    _alloca_probe
0x10041248f  sub     rsp, rax
0x100412492  mov     [rbp+16C0h+var_16C8], 0FFFFFFFFFFFFFFFEh
0x10041249a  mov     rax, cs:__security_cookie
0x1004124a1  xor     rax, rsp
0x1004124a4  mov     [rbp+16C0h+var_50], rax
0x1004124ab  mov     rsi, r9
0x1004124ae  mov     [rbp+16C0h+var_1720], r9
0x1004124b2  mov     r12, r8
0x1004124b5  mov     [rsp+17C0h+var_1780], r8
0x1004124ba  mov     r15d, edx
0x1004124bd  mov     [rsp+17C0h+var_1770], edx
0x1004124c1  mov     [rsp+17C0h+var_176C], ecx
0x1004124c5  mov     r14, [rbp+16C0h+arg_20]
0x1004124cc  mov     [rbp+16C0h+var_1718], r14
0x1004124d0  call    cs:__imp_GetXdbServerGlobals
0x1004124d6  cmp     dword ptr [rax+2ED0h], 0
0x1004124dd  jnz     short loc_100412531
0x1004124df  mov     rax, cs:qword_10049F340
0x1004124e6  test    byte ptr [rax+430h], 40h
0x1004124ed  jnz     short loc_100412531
0x1004124ef  mov     r8, gs:58h
0x1004124f8  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1004124ff  mov     ecx, [rax]
0x100412501  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100412508  mov     edx, [rax]
0x10041250a  add     rdx, [r8+rcx*8]
0x10041250e  mov     rax, [rdx]
0x100412511  test    rax, rax
0x100412514  jz      short loc_100412540
0x100412516  mov     rax, [rax+38h]
0x10041251a  mov     rcx, [rax]
0x10041251d  test    rcx, rcx
0x100412520  jz      short loc_100412540
0x100412522  mov     edx, 2186h
0x100412527  call    cs:__imp_?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z; CSessionTraceFlags::CheckSessionTraceInternal(CSessionTraceFlags *,ulong)
0x10041252d  test    eax, eax
0x10041252f  jz      short loc_100412540
0x100412531  call    cs:__imp_?GetReplicatedMasterDbId@@YAGXZ; GetReplicatedMasterDbId(void)
0x100412537  movzx   ecx, ax
0x10041253a  call    cs:__imp_?SetMasterDbId@@YAXG@Z; SetMasterDbId(ushort)
0x100412540  mov     edx, 3
0x100412545  lea     rcx, [rbp+16C0h+var_16C0]
0x100412549  call    cs:__imp_??0CaptureStartupPhaseTelemetry@@QEAA@H@Z; CaptureStartupPhaseTelemetry::CaptureStartupPhaseTelemetry(int)
0x10041254f  nop
0x100412550  call    ?InitXE@@YAXXZ; InitXE(void)
0x100412555  call    cs:__imp_?InitializeXeSosCallbacks@XeSosCallbacks@@SAXXZ; XeSosCallbacks::InitializeXeSosCallbacks(void)
0x10041255b  call    cs:__imp_?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ; SOS_OS::GetClientProcessGlobals(void)
0x100412561  mov     rbx, [rax]
0x100412564  call    cs:__imp_?GetXeSosIsEnabledCallbacks@XeSosCallbacks@@SAPEBQ6AHXZXZ; XeSosCallbacks::GetXeSosIsEnabledCallbacks(void)
0x10041256a  mov     rdx, rax
0x10041256d  mov     rcx, rbx
0x100412570  call    cs:__imp_?SetXeSosIsEnabledCallbacks@ProcessConfig@@QEAAXPEBQ6AHXZ@Z; ProcessConfig::SetXeSosIsEnabledCallbacks(int (*const *)(void))
0x100412576  call    cs:__imp_?GetXeSosPublishCallbacks@XeSosCallbacks@@SAPEBQ6AXPEAX@ZXZ; XeSosCallbacks::GetXeSosPublishCallbacks(void)
0x10041257c  mov     rdx, rax
0x10041257f  mov     rcx, rbx
0x100412582  call    cs:__imp_?SetXeSosPublishCallbacks@ProcessConfig@@QEAAXPEBQ6AXPEAX@Z@Z; ProcessConfig::SetXeSosPublishCallbacks(void (*const *)(void *))
0x100412588  call    cs:__imp_?GetXeSosIsCollectEventColumnEnabledCallbacks@XeSosCallbacks@@SAPEBQ6AHXZXZ; XeSosCallbacks::GetXeSosIsCollectEventColumnEnabledCallbacks(void)
0x10041258e  mov     rdx, rax
0x100412591  mov     rcx, rbx
0x100412594  call    cs:__imp_?SetXeSosIsCollectEventColumnEnabledCallbacks@ProcessConfig@@QEAAXPEBQ6AHXZ@Z; ProcessConfig::SetXeSosIsCollectEventColumnEnabledCallbacks(int (*const *)(void))
0x10041259a  call    cs:__imp_SvlSystemBoot
0x1004125a0  mov     ebx, eax
0x1004125a2  test    eax, eax
0x1004125a4  jns     short loc_1004125EF
0x1004125a6  lfence
0x1004125a9  mov     ecx, eax
0x1004125ab  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x1004125b1  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x1004125b7  mov     r9, rax; struct __crt_locale_pointers *
0x1004125ba  mov     dword ptr [rsp+17C0h+var_1798], ebx
0x1004125be  lea     rbx, aSvlLibraryPost; "SVL library post-boot initialization"
0x1004125c5  mov     [rsp+17C0h+var_17A0], rbx
0x1004125ca  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x1004125d1  mov     edx, 200h; unsigned __int64
0x1004125d6  lea     rcx, [rbp+16C0h+var_1670]; Buffer
0x1004125da  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x1004125df  test    eax, eax
0x1004125e1  mov     rcx, rbx
0x1004125e4  js      short loc_1004125EA
0x1004125e6  lea     rcx, [rbp+16C0h+var_1670]; char *
0x1004125ea  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x1004125ef  xor     edi, edi
0x1004125f1  mov     rax, cs:qword_10049F360
0x1004125f8  mov     [rax+38BCh], edi
0x1004125fe  test    r15b, 1
0x100412602  jz      short loc_100412643
0x100412604  mov     rax, cs:qword_10049F360
0x10041260b  test    dword ptr [rax+0BD7Ch], 2000h
0x100412615  jnz     short loc_10041264A
0x100412617  cmp     [rax+38A8h], edi
0x10041261d  jz      short loc_10041265B
0x10041261f  xor     r8d, r8d
0x100412622  lea     rdx, aReducedfootpri; "ReducedFootprintForLogicalMaster"
0x100412629  lea     rcx, aSqlConfig; "SQL.Config"
0x100412630  call    cs:__imp_HostReg_IsFeatureSwitchOn
0x100412636  test    al, al
0x100412638  jz      short loc_100412654
0x10041263a  call    ?IsLogicalMaster@@YA_NXZ; IsLogicalMaster(void)
0x10041263f  test    al, al
0x100412641  jz      short loc_100412654
0x100412643  mov     rax, cs:qword_10049F360
0x10041264a  mov     dword ptr [rax+38BCh], 1
0x100412654  mov     rax, cs:qword_10049F360
0x10041265b  mov     r13d, r15d
0x10041265e  and     r13d, 8000h
0x100412665  jnz     short loc_100412676
0x100412667  cmp     [rax+38A8h], edi
0x10041266d  setnz   cl
0x100412670  call    cs:__imp_?InitXeForSqlLang@@YAX_N@Z; InitXeForSqlLang(bool)
0x100412676  call    cs:__imp_?InitAdhocXESessionSupport@@YAXXZ; InitAdhocXESessionSupport(void)
0x10041267c  call    cs:__imp_?InitXeForSqlmin@@YAXXZ; InitXeForSqlmin(void)
0x100412682  mov     rax, cs:qword_10049F360
0x100412689  cmp     [rax+38A8h], edi
0x10041268f  setnz   cl
0x100412692  call    cs:__imp_?InitXeForQds@@YAX_N@Z; InitXeForQds(bool)
0x100412698  nop
0x100412699  lea     rcx, [rbp+16C0h+var_16C0]
0x10041269d  call    cs:__imp_??1CaptureStartupPhaseTelemetry@@QEAA@XZ; CaptureStartupPhaseTelemetry::~CaptureStartupPhaseTelemetry(void)
0x1004126a3  mov     rax, cs:qword_10049F360
0x1004126aa  cmp     dword ptr [rax+38B0h], 0
0x1004126b1  jz      short loc_1004126C0
0x1004126b3  call    cs:__imp_ServiceFabricInit
0x1004126b9  mov     rax, cs:qword_10049F360
0x1004126c0  cmp     dword ptr [rax+38A8h], 0
0x1004126c7  jz      short loc_1004126CF
0x1004126c9  call    cs:__imp_HadrFabricInit
0x1004126cf  mov     [rsp+17C0h+var_1798], rdi; wchar_t *
0x1004126d4  lea     rax, qword_1004D28E0
0x1004126db  mov     [rsp+17C0h+var_17A0], rax; void *
0x1004126e0  lea     r9, ?TraceFlagUpdateCallback@@YAXPEB_W00PEAX@Z; void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *)
0x1004126e7  lea     r8, aBasetraceflags; "BaseTraceFlags"
0x1004126ee  lea     rdx, aSql; "SQL"
0x1004126f5  mov     rcx, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1004126fc  mov     rcx, [rcx]; this
0x1004126ff  call    ?SubscribeAndGetDynamicStringSetting@IServerConfiguration@@QEAA_NPEB_W0P6AX000PEAX@Z10@Z; IServerConfiguration::SubscribeAndGetDynamicStringSetting(wchar_t const *,wchar_t const *,void (*)(wchar_t const *,wchar_t const *,wchar_t const *,void *),void *,wchar_t const *)
0x100412704  mov     [rsp+17C0h+var_1798], rdi; wchar_t *
0x100412709  lea     rax, qword_1004D3060
0x100412710  mov     [rsp+17C0h+var_17A0], rax; void *
0x100412715  lea     r9, ?TraceFlagUpdateCallback@@YAXPEB_W00PEAX@Z; void (*)(const wchar_t *, const wchar_t *, const wchar_t *, void *)
0x10041271c  lea     r8, aTraceflags; "TraceFlags"
0x100412723  lea     rdx, aSql; "SQL"
0x10041272a  mov     rcx, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100412731  mov     rcx, [rcx]; this
0x100412734  call    ?SubscribeAndGetDynamicStringSetting@IServerConfiguration@@QEAA_NPEB_W0P6AX000PEAX@Z10@Z; IServerConfiguration::SubscribeAndGetDynamicStringSetting(wchar_t const *,wchar_t const *,void (*)(wchar_t const *,wchar_t const *,wchar_t const *,void *),void *,wchar_t const *)
0x100412739  mov     ecx, 1
0x10041273e  call    cs:__imp_?Init@CFeatureSwitchesDk@@SAXW4CFeatureSwitchesExecEnv@@@Z; CFeatureSwitchesDk::Init(CFeatureSwitchesExecEnv)
0x100412744  mov     ecx, 1
0x100412749  call    cs:__imp_?Init@CFeatureSwitchesTsEs@@SAXW4CFeatureSwitchesExecEnv@@@Z; CFeatureSwitchesTsEs::Init(CFeatureSwitchesExecEnv)
0x10041274f  mov     ecx, 1
0x100412754  call    cs:__imp_?Init@CFeatureSwitchesMin@@SAXW4CFeatureSwitchesExecEnv@@@Z; CFeatureSwitchesMin::Init(CFeatureSwitchesExecEnv)
0x10041275a  mov     ecx, 1
0x10041275f  call    cs:__imp_?Init@CFeatureSwitchesTds@@SAXW4CFeatureSwitchesExecEnv@@@Z; CFeatureSwitchesTds::Init(CFeatureSwitchesExecEnv)
0x100412765  mov     ecx, 1
0x10041276a  call    cs:__imp_?Init@CFeatureSwitchesQds@@SAXW4CFeatureSwitchesExecEnv@@@Z; CFeatureSwitchesQds::Init(CFeatureSwitchesExecEnv)
0x100412770  mov     ecx, 1
0x100412775  call    cs:__imp_?Init@CFeatureSwitchesLangSvc@@SAXW4CFeatureSwitchesExecEnv@@@Z; CFeatureSwitchesLangSvc::Init(CFeatureSwitchesExecEnv)
0x10041277b  mov     ecx, 1
0x100412780  call    cs:__imp_?Init@CFeatureSwitchesFido@@SAXW4CFeatureSwitchesExecEnv@@@Z; CFeatureSwitchesFido::Init(CFeatureSwitchesExecEnv)
0x100412786  mov     ecx, 1
0x10041278b  call    cs:__imp_?Init@CFeatureSwitchesBluemoon@@SAXW4CFeatureSwitchesExecEnv@@@Z; CFeatureSwitchesBluemoon::Init(CFeatureSwitchesExecEnv)
0x100412791  call    cs:__imp_?ExportCurrentInstance@CFeatureSwitchesQds@@SAPEBV1@XZ; CFeatureSwitchesQds::ExportCurrentInstance(void)
0x100412797  mov     rbx, rax
0x10041279a  call    cs:__imp_?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ; CFeatureSwitchesMin::ExportCurrentInstance(void)
0x1004127a0  mov     rcx, rax
0x1004127a3  mov     rdx, rbx
0x1004127a6  call    cs:__imp_?SQLLangImportFeatureSwitches@@YAXPEBVCFeatureSwitchesMin@@PEBVCFeatureSwitchesQds@@@Z; SQLLangImportFeatureSwitches(CFeatureSwitchesMin const *,CFeatureSwitchesQds const *)
0x1004127ac  mov     rax, cs:qword_10049F360
0x1004127b3  cmp     dword ptr [rax+38A8h], 0
0x1004127ba  jz      short loc_1004127E2
0x1004127bc  mov     ecx, 1
0x1004127c1  call    cs:__imp_?Init@CFeatureSwitchesFabric@@SAXW4CFeatureSwitchesExecEnv@@@Z; CFeatureSwitchesFabric::Init(CFeatureSwitchesExecEnv)
0x1004127c7  call    cs:__imp_?ExportCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::ExportCurrentInstance(void)
0x1004127cd  mov     rbx, rax
0x1004127d0  call    cs:__imp_?ExportCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ; CFeatureSwitchesMin::ExportCurrentInstance(void)
0x1004127d6  mov     rcx, rax
0x1004127d9  mov     rdx, rbx
0x1004127dc  call    cs:__imp_HadrFabricImportFeatureSwitches
0x1004127e2  mov     rax, cs:qword_10049F360
0x1004127e9  cmp     dword ptr [rax+38A8h], 0
0x1004127f0  jz      loc_100412887
0x1004127f6  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ; CFeatureSwitchesMin::GetCurrentInstance(void)
0x1004127fc  cmp     byte ptr [rax+2B5h], 0
0x100412803  jnz     short loc_100412814
0x100412805  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesLangSvc@@SAPEBV1@XZ; CFeatureSwitchesLangSvc::GetCurrentInstance(void)
0x10041280b  cmp     byte ptr [rax+38Dh], 0
0x100412812  jz      short loc_100412887
0x100412814  call    cs:__imp_?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ; InstanceConfigStoreManager::GetInstanceConfigStoreManager(void)
0x10041281a  mov     rcx, rax
0x10041281d  call    cs:__imp_?PostInit@InstanceConfigStoreManager@@QEAAJXZ; InstanceConfigStoreManager::PostInit(void)
0x100412823  mov     ebx, eax
0x100412825  test    eax, eax
0x100412827  jns     short loc_100412878
0x100412829  lfence
0x10041282c  mov     ecx, eax
0x10041282e  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x100412834  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x10041283a  mov     r9, rax; struct __crt_locale_pointers *
0x10041283d  mov     dword ptr [rsp+17C0h+var_1798], ebx
0x100412841  lea     rbx, aInstanceConfig_0; "Instance Config Store Manager post init"...
0x100412848  mov     [rsp+17C0h+var_17A0], rbx
0x10041284d  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x100412854  mov     edx, 200h; unsigned __int64
0x100412859  lea     rcx, [rbp+16C0h+var_1470]; Buffer
0x100412860  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAU__crt_locale_pointers@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,__crt_locale_pointers *,...)
0x100412865  test    eax, eax
0x100412867  mov     rcx, rbx
0x10041286a  js      short loc_100412873
0x10041286c  lea     rcx, [rbp+16C0h+var_1470]; char *
0x100412873  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100412878  call    cs:__imp_?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ; InstanceConfigStoreManager::GetInstanceConfigStoreManager(void)
0x10041287e  mov     rcx, rax
0x100412881  call    cs:__imp_?ParsePropertyBag@InstanceConfigStoreManager@@QEAAXXZ; InstanceConfigStoreManager::ParsePropertyBag(void)
0x100412887  mov     rax, cs:qword_10049F360
0x10041288e  cmp     dword ptr [rax+38A8h], 0
0x100412895  jz      short loc_1004128CC
0x100412897  call    cs:__imp_GetXdbServerGlobals
0x10041289d  cmp     dword ptr [rax+2EE0h], 0
0x1004128a4  jz      short loc_1004128CC
0x1004128a6  xor     edx, edx
0x1004128a8  lea     rcx, aCCertFabriccli; "c:\\cert\\fabricClientCert.pfx"
0x1004128af  call    cs:__imp_?LoadCertificateAndAddToStore@@YAJPEB_W0@Z; LoadCertificateAndAddToStore(wchar_t const *,wchar_t const *)
0x1004128b5  test    eax, eax
0x1004128b7  jns     short loc_1004128CC
0x1004128b9  lea     rdx, aCertificateLoa; "Certificate load for SQLPAL failed.\n"
0x1004128c0  lea     rcx, aLs; "%ls"
0x1004128c7  call    ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x1004128cc  call    ?InitXdbSrvGlobals@@YAXXZ; InitXdbSrvGlobals(void)
0x1004128d1  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1004128d8  mov     rcx, [rax]
0x1004128db  mov     rax, [rcx]
0x1004128de  mov     [rsp+17C0h+var_1798], rdi
0x1004128e3  mov     byte ptr [rsp+17C0h+var_17A0], 1
0x1004128e8  lea     r9, dword_1004A0A18
0x1004128ef  lea     r8, aMaxretry; "MaxRetry"
0x1004128f6  lea     rdx, aXevent; "XEvent"
0x1004128fd  call    qword ptr [rax+208h]
0x100412903  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ; CFeatureSwitchesMin::GetCurrentInstance(void)
0x100412909  mov     rcx, cs:qword_10049F340
0x100412910  cmp     byte ptr [rax+4ECh], 0
0x100412917  jnz     short loc_100412922
0x100412919  test    byte ptr [rcx+58Fh], 8
0x100412920  jz      short loc_10041292B
0x100412922  test    byte ptr [rcx+58Fh], 10h
0x100412929  jz      short loc_100412953
0x10041292b  call    cs:__imp_?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ; CFeatureSwitchesMin::GetCurrentInstance(void)
0x100412931  mov     rcx, cs:qword_10049F340
0x100412938  cmp     byte ptr [rax+4E1h], 0
0x10041293f  jnz     short loc_10041294A
0x100412941  cmp     byte ptr [rcx+68Bh], 0
0x100412948  jge     short loc_100412974
0x10041294a  test    byte ptr [rcx+68Ch], 1
0x100412951  jnz     short loc_100412974
0x100412953  mov     ecx, 2C7Ah
0x100412958  xor     edx, edx
0x10041295a  call    cs:__imp_?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOn(ushort,CGlobalTraceFlags::FlagUsage)
0x100412960  mov     ecx, 2C80h
0x100412965  xor     edx, edx
0x100412967  call    cs:__imp_?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z; CGlobalTraceFlags::TurnOn(ushort,CGlobalTraceFlags::FlagUsage)
0x10041296d  mov     rcx, cs:qword_10049F340
0x100412974  test    byte ptr [rcx+58Fh], 4
0x10041297b  jz      loc_100412B19
0x100412981  mov     rdx, gs:58h
0x10041298a  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100412991  mov     ecx, [rax]
0x100412993  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10041299a  mov     ebx, [rax]
0x10041299c  add     rbx, [rdx+rcx*8]
0x1004129a0  mov     rax, [rbx+100h]
0x1004129a7  test    rax, rax
0x1004129aa  jnz     short loc_1004129BB
0x1004129ac  xor     ecx, ecx
0x1004129ae  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x1004129b4  mov     rax, [rbx+100h]
0x1004129bb  mov     rax, [rax+3E0h]
0x1004129c2  mov     rcx, [rax+140h]
0x1004129c9  call    cs:__imp_?CreateGlobalInstance@IOCompletionPortThreadPool@@SAJPEAVIMemObj@@@Z; IOCompletionPortThreadPool::CreateGlobalInstance(IMemObj *)
0x1004129cf  mov     ebx, eax
0x1004129d1  test    eax, eax
0x1004129d3  jns     short loc_100412A24
0x1004129d5  lfence
0x1004129d8  mov     ecx, eax
0x1004129da  call    cs:__imp_?SetWin32ExitCode@@YAXK@Z; SetWin32ExitCode(ulong)
0x1004129e0  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x1004129e6  mov     r9, rax; struct __crt_locale_pointers *
0x1004129e9  mov     dword ptr [rsp+17C0h+var_1798], ebx
0x1004129ed  lea     rbx, aFailedToInitia; "Failed to initialize IOCompletionPortTh"...
0x1004129f4  mov     [rsp+17C0h+var_17A0], rbx
0x1004129f9  lea     r8, aHsHresult0xX; "%hs (HRESULT 0x%x)"
0x100412a00  mov     edx, 200h; unsigned __int64
  ... truncated ...
```

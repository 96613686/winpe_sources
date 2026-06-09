# ConfigureDK(void)

- ea: `0x100413d90`
- end: `0x10041573e`
- name: `?ConfigureDK@@YAXXZ`
- size: `6574`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100416770`

## callees

- `0x100401580`
- `0x100401800`
- `0x100401aa0`
- `0x100402080`
- `0x1004021d0`
- `0x100402ec0`
- `0x100408810`
- `0x100413d90`
- `0x1004187d0`
- `0x10041d320`
- `0x10041d4f0`
- `0x10041eac0`
- `0x1004403d0`
- `0x1004404f0`
- `0x100440860`
- `0x10044aad0`
- `0x10044ce60`
- `0x10044cf40`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x100413ee9`
- `KERNEL32!SetThreadPriority` at `0x100413f7c`
- `KERNEL32!SetThreadPriority` at `0x100413ee9`
- `KERNEL32!SetThreadPriority` at `0x100413f7c`
- `KERNEL32!GetProcAddress` at `0x100414bc1`
- `KERNEL32!GetProcAddress` at `0x100414bc1`
- `KERNEL32!SetPriorityClass` at `0x100413ed3`
- `KERNEL32!SetPriorityClass` at `0x100413f66`
- `KERNEL32!SetPriorityClass` at `0x100413ed3`
- `KERNEL32!SetPriorityClass` at `0x100413f66`
- `KERNEL32!GetCurrentThread` at `0x100413edd`
- `KERNEL32!GetCurrentThread` at `0x100413f70`
- `KERNEL32!GetCurrentThread` at `0x100413edd`
- `KERNEL32!GetCurrentThread` at `0x100413f70`
- `KERNEL32!GetPriorityClass` at `0x100413f39`
- `KERNEL32!GetPriorityClass` at `0x100413f39`
- `KERNEL32!GlobalMemoryStatusEx` at `0x100413ff3`
- `KERNEL32!GlobalMemoryStatusEx` at `0x10041445c`
- `KERNEL32!GlobalMemoryStatusEx` at `0x100413ff3`
- `KERNEL32!GlobalMemoryStatusEx` at `0x10041445c`
- `KERNEL32!GetModuleHandleW` at `0x100414bb1`
- `KERNEL32!GetModuleHandleW` at `0x1004153fa`
- `KERNEL32!GetModuleHandleW` at `0x100415430`
- `KERNEL32!GetModuleHandleW` at `0x100415466`
- `KERNEL32!GetModuleHandleW` at `0x10041549c`
- `KERNEL32!GetModuleHandleW` at `0x100414bb1`
- `KERNEL32!GetModuleHandleW` at `0x1004153fa`
- `KERNEL32!GetModuleHandleW` at `0x100415430`
- `KERNEL32!GetModuleHandleW` at `0x100415466`
- `KERNEL32!GetModuleHandleW` at `0x10041549c`
- `KERNEL32!SetProcessPriorityBoost` at `0x10041521d`
- `KERNEL32!SetProcessPriorityBoost` at `0x10041521d`
- `KERNEL32!GetModuleHandleA` at `0x1004153c0`
- `KERNEL32!GetModuleHandleA` at `0x1004153c0`
- `KERNEL32!GetLastError` at `0x100413ef7`
- `KERNEL32!GetLastError` at `0x100413f86`
- `KERNEL32!GetLastError` at `0x100413ef7`
- `KERNEL32!GetLastError` at `0x100413f86`
- `KERNEL32!GetCurrentProcess` at `0x100413ec6`
- `KERNEL32!GetCurrentProcess` at `0x100413f30`
- `KERNEL32!GetCurrentProcess` at `0x100413f5a`
- `KERNEL32!GetCurrentProcess` at `0x100415211`
- `KERNEL32!GetCurrentProcess` at `0x100413ec6`
- `KERNEL32!GetCurrentProcess` at `0x100413f30`
- `KERNEL32!GetCurrentProcess` at `0x100413f5a`
- `KERNEL32!GetCurrentProcess` at `0x100415211`
- `sqlmin!?GetGlobalBufferPool@@YAAEAVBPool@@XZ` at `0x10041537f`
- `sqlmin!?GetGlobalBufferPool@@YAAEAVBPool@@XZ` at `0x10041537f`
- `sqlmin!?ReadConfig@BPool@@QEAAXXZ` at `0x100415388`
- `sqlmin!?ReadConfig@BPool@@QEAAXXZ` at `0x100415388`
- `sqlmin!?GetVirtualMachineType@HwInfo@@SA?AW4VirtualMachineType@1@XZ` at `0x1004152af`
- `sqlmin!?GetVirtualMachineType@HwInfo@@SA?AW4VirtualMachineType@1@XZ` at `0x1004152af`
- `sqlmin!?VetoableCpuChangeCallback@StartUp@@SA?AVSystemAffinity@@V2@0@Z` at `0x10041527b`
- `sqlmin!?OnThrottlePendingIO@FCB@@SAXPEAVSOS_IOCompRequest@@HH@Z` at `0x100414743`
- `sqlmin!?IssuePendingIO@FCB@@SAHPEAVSOS_IOCompRequest@@PEAV?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@@Z` at `0x100414733`
- `sqlmin!?IHashWHostDefault@@YAKPEBE_K@Z` at `0x100414722`
- `sqlmin!?FEqWszHostDefault@@YAHPEB_W0@Z` at `0x1004146f7`
- `sqlmin!?GetBPoolOverheadBytes@@YA_KXZ` at `0x100414644`
- `sqlmin!?GetBPoolOverheadBytes@@YA_KXZ` at `0x100414644`
- `sqlmin!?IsAWE_SKU@SysConfigPagePtr@@SAHXZ` at `0x10041460a`
- `sqlmin!?IsAWE_SKU@SysConfigPagePtr@@SAHXZ` at `0x10041460a`
- `sqlmin!?ReadNodeConfiguration@StartUp@@SAXQEAVGroupAffinity@@PEAF@Z` at `0x10041421e`
- `sqlmin!?ReadNodeConfiguration@StartUp@@SAXQEAVGroupAffinity@@PEAF@Z` at `0x10041421e`
- `sqlmin!?DBGetOverlappedResult@@YAHPEAXPEAU_OVERLAPPED@@PEAKH@Z` at `0x1004141d6`
- `sqlmin!?stackTraceCallBack@@YAXPEAXPEB_WKPEAVCDStream@@@Z` at `0x10041412c`
- `sqlmin!?SetSOSStartTime@CSysInfoTable@@SAXAEBUSQLDATE@@@Z` at `0x100413e8d`
- `sqlmin!?SetSOSStartTime@CSysInfoTable@@SAXAEBUSQLDATE@@@Z` at `0x100413e8d`
- `sqlmin!?utgettime@@YAXPEAUSQLDATEBASE@@HPEA_N@Z` at `0x100413e82`
- `sqlmin!?utgettime@@YAXPEAUSQLDATEBASE@@HPEA_N@Z` at `0x100413e82`
- `sqlmin!?Bootstrap@SysConfigPagePtr@@QEAAXXZ` at `0x100413dfb`
- `sqlmin!?Bootstrap@SysConfigPagePtr@@QEAAXXZ` at `0x100413dfb`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x1004143bf`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100414462`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x1004147aa`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100414a83`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100414b4a`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100414b73`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x1004143bf`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100414462`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x1004147aa`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100414a83`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100414b4a`
- `sqlmin!?GetCurrentInstance@CFeatureSwitchesMin@@SAPEBV1@XZ` at `0x100414b73`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100413dda`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100413e98`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100414251`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100413dda`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100413e98`
- `sqlmin!?FUseReplicatedServerContext@@YA_NXZ` at `0x100414251`
- `sqlmin!GetXdbServerGlobals` at `0x1004142cf`
- `sqlmin!GetXdbServerGlobals` at `0x1004142eb`
- `sqlmin!GetXdbServerGlobals` at `0x1004142f9`
- `sqlmin!GetXdbServerGlobals` at `0x10041436f`
- `sqlmin!GetXdbServerGlobals` at `0x100414799`
- `sqlmin!GetXdbServerGlobals` at `0x1004147b7`
- `sqlmin!GetXdbServerGlobals` at `0x100414865`
- `sqlmin!GetXdbServerGlobals` at `0x1004148e7`
- `sqlmin!GetXdbServerGlobals` at `0x1004148fe`
- `sqlmin!GetXdbServerGlobals` at `0x100414914`
- `sqlmin!GetXdbServerGlobals` at `0x1004156ea`
- `sqlmin!GetXdbServerGlobals` at `0x1004142cf`
- `sqlmin!GetXdbServerGlobals` at `0x1004142eb`
- `sqlmin!GetXdbServerGlobals` at `0x1004142f9`
- `sqlmin!GetXdbServerGlobals` at `0x10041436f`
- `sqlmin!GetXdbServerGlobals` at `0x100414799`
- `sqlmin!GetXdbServerGlobals` at `0x1004147b7`
- `sqlmin!GetXdbServerGlobals` at `0x100414865`
- `sqlmin!GetXdbServerGlobals` at `0x1004148e7`
- `sqlmin!GetXdbServerGlobals` at `0x1004148fe`
- `sqlmin!GetXdbServerGlobals` at `0x100414914`
- `sqlmin!GetXdbServerGlobals` at `0x1004156ea`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100414e90`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100414e90`
- `sqllang!?SymbolizeFrames@@YAHPEBQEAXIPEADI@Z` at `0x1004141b4`
- `sqllang!?ex_exception_postcallback@@YAXHHHH@Z` at `0x100414170`
- `sqllang!?ex_exception_precallback@@YAXPEAH000PEAXPEAD@Z` at `0x10041415f`
- `sqllang!?ex_sqltrace_event@@YAXIIIIPEA_WI@Z` at `0x10041410a`
- `sqllang!?DbgEngineStackBackTrace@@YAGKKPEAPEAXPEAK@Z` at `0x100414049`
- `sqllang!?IsDACAvailable@@YAHPEB_W@Z` at `0x100414e3e`
- `sqllang!?IsDACAvailable@@YAHPEB_W@Z` at `0x100414e3e`
- `sqldk!?SOS_OS_MinHealthyRateOfMemReleaseKB@@3_JA` at `0x1004148f4`
- `sqldk!?sm_BootFinalize@SOS_PublicGlobals@@2P6A?AW4SOS_RESULT@@XZEA` at `0x100413e73`
- `sqldk!?SOS_OS_StackBackTraceRoutine@@3P6AGKKPEAPEAXPEAK@ZEA` at `0x100414042`
- `sqldk!?SOS_OS_CriticalExceptionCheckRoutine@@3P6AXI@ZEA` at `0x1004141c5`
- `sqldk!?SOS_OS_JobLowMemorySignalThresholdBytes@@3_KA` at `0x1004147fe`
- `sqldk!?SOS_OS_JobLowMemorySignalThresholdBytes@@3_KA` at `0x100414872`
- `sqldk!?SOS_OS_JobLowMemorySignalThresholdBytes@@3_KA` at `0x1004148dd`
- `sqldk!?SOS_OS_UserLogRoutine@@3P6AXHHHKZZEA` at `0x10041414e`
- `sqldk!?sm_IdleOfflineTimeOut@SOS_PublicGlobals@@2KA` at `0x1004149e6`
- `sqldk!?sm_IdleOfflineTimeOut@SOS_PublicGlobals@@2KA` at `0x1004149f3`
- `sqldk!?SOS_OS_IgnoreNonYieldingScheduler@@3HA` at `0x10041490b`
- `sqldk!?SOS_OS_ShouldStackDumpForErrorCallBack@@3P6AHKH@ZEA` at `0x10041411b`
- `sqldk!?sm_NodeLsSize@SOS_PublicGlobals@@2FA` at `0x1004146d2`
- `sqldk!?SOS_OS_MinSosGapWithJobMemLimitInBytes@@3_KA` at `0x1004147c4`
- `sqldk!?SOS_OS_MinSosGapWithJobMemLimitInBytes@@3_KA` at `0x1004147de`
- `sqldk!?SOS_OS_MinSosGapWithJobMemLimitInBytes@@3_KA` at `0x10041485b`
- `sqldk!?SOS_OS_MinSosGapWithJobMemLimitInBytes@@3_KA` at `0x100414882`
- `sqldk!?sm_NodeInit@SOS_PublicGlobals@@2P6A?AW4SOS_RESULT@@QEAVSOS_Node@@@ZEA` at `0x100413e56`
- `sqldk!?SOS_OS_WorkerHighUtilizationThreshold@@3IA` at `0x10041565b`
- `sqldk!?sm_IdleOfflineTimeOutTicks@SOS_PublicGlobals@@2V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@A` at `0x1004149fa`
- `sqldk!?sm_osSystemAffinity@SOS_PublicGlobals@@2VSystemAffinity@@A` at `0x10041569c`
- `sqldk!?sm_MaxWorkers@SOS_PublicGlobals@@2IA` at `0x100414941`
- `sqldk!?SOS_OS_ExPostCallBackRoutine@@3P6AXHHHH@ZEA` at `0x100414169`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100414982`
- `sqldk!?sm_IdleServerEventCallbackList@SOS_PublicGlobals@@2V?$TCallbackList@V?$TCallback@XW4WakeUpReason@@KVNullType@@V2@@@@@A` at `0x100414d44`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x1004140d7`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x100414ad9`
- `sqldk!?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA` at `0x100414b20`
- `sqldk!?SOS_OS_ExceptionPrintRoutine@@3P6AXHHHPEAD@ZEA` at `0x10041413d`
- `sqldk!?SOS_OS_VetoableCpuChangeRoutine@@3P6A?AVSystemAffinity@@V1@0@ZEA` at `0x100415272`
- `sqldk!?SOS_OS_ProcessStarvedUtilizationThreshold@@3IA` at `0x100415686`
- `sqldk!?MemoryNode_LargePageSize@@3_KA` at `0x10041452d`
- `sqldk!?sm_SetAbortCallbackList@SOS_PublicGlobals@@2V?$TCallbackList@V?$TCallback@XPEAVSOS_Task@@VNullType@@V2@V2@@@@@A` at `0x100414bdf`
- `sqldk!?SOS_OS_SharedMemoryContextExternalFragmentCount@@3HA` at `0x100414661`
- `sqldk!?sm_SchedLsSize@SOS_PublicGlobals@@2FA` at `0x1004146e6`
- `sqldk!?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA` at `0x1004140e8`
- `sqldk!?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA` at `0x100414aca`
- `sqldk!?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA` at `0x100414b11`
- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x100414b69`
- `sqldk!?SOS_OS_ExPreCallBackRoutine@@3P6AXPEAH000PEAXPEAD@ZEA` at `0x100414158`
- `sqldk!?sm_IdleTimeOutTicks@SOS_PublicGlobals@@2V?$SOS_Ticks@V?$InterruptTicks@_K@@$0?2@@A` at `0x1004149aa`
- `sqldk!?sm_CommonCriteriaModeEnabled@SOS_PublicGlobals@@2HA` at `0x100414f6d`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10041405a`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100414270`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10041449b`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1004144ca`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10041451d`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100414597`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100414610`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100414dd8`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100414e02`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100414f94`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100414fac`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100415257`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100415285`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10041529f`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1004152de`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100415342`
- `sqldk!?m_CollectingStatistics@CommonGlobalState@@2_NA` at `0x100413e27`
- `sqldk!?SOS_OS_NumDACCount@@3KA` at `0x100414f38`
- `sqldk!?SOS_OS_CreateTraceBuffRoutine@@3P6APEAVSOS_TraceStreamBuffer@@PEAVIMemObj@@@ZEA` at `0x1004140a2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041553a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004155b2`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10041553a`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1004155b2`
- `sqldk!SystemThread_TlsOffset` at `0x1004154ef`
- `sqldk!SystemThread_TlsOffset` at `0x100415521`
- `sqldk!SystemThread_TlsOffset` at `0x100415565`
- `sqldk!SystemThread_TlsOffset` at `0x100415597`
- `sqldk!SystemThread_TlsIndex` at `0x1004154e6`
- `sqldk!SystemThread_TlsIndex` at `0x100415518`
- `sqldk!SystemThread_TlsIndex` at `0x10041555c`
- `sqldk!SystemThread_TlsIndex` at `0x10041558e`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x100413fc5`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@KK@Z` at `0x100413fc5`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x10041468b`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x1004152d4`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x10041468b`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x1004152d4`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100414e5f`

## string_xrefs

- `0x100415425`: `sqldk.dll`
- `0x10041544a`: `sqldk.dll`
- `0x1004153ef`: `sqlmin.dll`
- `0x100415414`: `sqlmin.dll`
- `0x10041545b`: `sqllang.dll`
- `0x100415480`: `sqllang.dll`
- `0x100415491`: `sqltses.dll`
- `0x1004154b6`: `sqltses.dll`
- `0x10041435f`: `SQL.Config`
- `0x100414387`: `SQL.Config`
- `0x10041504e`: `SQL.Config`
- `0x100415087`: `SQL.Config`
- `0x1004150c0`: `SQL.Config`
- `0x1004150f9`: `SQL.Config`
- `0x100415132`: `SQL.Config`
- `0x10041516b`: `SQL.Config`
- `0x1004151a4`: `SQL.Config`
- `0x1004143e0`: `Enabling small memory environment configuration.`
- `0x100414baa`: `kernel32.dll`
- `0x100415071`: `Trace flag %d is ON. Use Yukon RTM cache limits.\n`
- `0x100415047`: `YukonRtmCacheLimits`
- `0x1004150e3`: `Trace flag %d is ON. Enable SOS task preallocation.\n`
- `0x1004150b9`: `TaskPreallocation`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
void ConfigureDK(void)
{
  SysConfigPagePtr *v0; // rcx
  int v1; // ecx
  bool v2; // cl
  char *v3; // rax
  HANDLE CurrentProcess; // rax
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  wchar_t *OSErrString; // rax
  __int64 v8; // rcx
  HANDLE v9; // rax
  DWORD PriorityClass; // ebx
  HANDLE v11; // rax
  HANDLE v12; // rax
  DWORD v13; // eax
  wchar_t *v14; // rax
  int v15; // esi
  int v16; // ecx
  __int64 v17; // rax
  int v18; // ecx
  char *v19; // rbx
  __int64 v20; // rdi
  RESOURCE *v21; // rax
  __int16 v22; // dx
  bool v23; // al
  char *v24; // r12
  int v25; // r14d
  struct IServerConfiguration *v26; // rdx
  __int64 v27; // rcx
  bool v28; // zf
  __int64 v29; // rdx
  _DWORD *v30; // rax
  __int64 v31; // rdx
  __int64 XdbServerGlobals; // rax
  char IsFeatureSwitchOn; // bl
  __int64 v34; // rdx
  __int64 v35; // rcx
  bool v36; // al
  RESOURCE *v37; // rax
  __int64 v38; // rcx
  int v39; // edi
  int IsAWE_SKU; // ebx
  int v41; // ebx
  __int64 v42; // rdx
  unsigned int v43; // ebx
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  char v47; // bl
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // r15
  unsigned __int64 *v53; // rax
  unsigned __int64 v54; // r15
  unsigned __int64 v55; // r13
  SIZE_T v56; // rbx
  __int64 v57; // rdx
  unsigned __int64 v58; // rcx
  __int64 v59; // r15
  unsigned __int64 *v60; // rax
  unsigned __int64 v61; // r15
  SIZE_T v62; // rbx
  __int64 TotalPagesCommitted; // rax
  __int64 v64; // rdx
  __int64 v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rdx
  unsigned __int64 v68; // rcx
  unsigned __int64 v69; // r8
  _BOOL8 v70; // rcx
  __int64 v71; // rcx
  unsigned __int64 v72; // rbx
  __int64 v73; // r8
  unsigned __int64 v74; // rcx
  unsigned __int64 v75; // rax
  unsigned __int64 v76; // rax
  void (*v77)(const wchar_t *, ...); // r8
  void (*v78)(const wchar_t *, ...); // r8
  __int64 v79; // rcx
  HMODULE ModuleHandleW; // rax
  const wchar_t *v81; // rax
  int v82; // edx
  char *v83; // rbx
  struct __crt_locale_pointers *DefaultLocale; // rax
  signed int v85; // eax
  signed int v86; // ebx
  struct __crt_locale_pointers *v87; // rax
  int v88; // eax
  char *v89; // rcx
  unsigned int v90; // edi
  unsigned int v91; // ebx
  __int64 v92; // rax
  HANDLE v93; // rax
  int v94; // ecx
  int v95; // ebx
  _DWORD *v96; // rdx
  int v97; // eax
  int v98; // eax
  BPool *GlobalBufferPool; // rax
  HMODULE ModuleHandleA; // rax
  HMODULE v101; // rax
  HMODULE v102; // rax
  HMODULE v103; // rax
  HMODULE v104; // rax
  __int64 v105; // rdx
  __int64 v106; // rax
  __int64 v107; // rbx
  __int64 v108; // rcx
  __int64 v109; // rdx
  __int64 v110; // rax
  __int64 v111; // rbx
  __int64 v112; // rax
  __int64 v113; // rbx
  int v114; // r8d
  double CPUCorePercentCap; // xmm6_8
  unsigned int CPUCount; // ebx
  __int64 v117; // rdx
  __int64 v118; // rcx
  __int64 v119; // rax
  int v120; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v121; // [rsp+34h] [rbp-CCh] BYREF
  int v122; // [rsp+38h] [rbp-C8h]
  DWORD v123; // [rsp+40h] [rbp-C0h] BYREF
  BYTE v124[4]; // [rsp+44h] [rbp-BCh] BYREF
  HKEY v125; // [rsp+48h] [rbp-B8h] BYREF
  int v126; // [rsp+50h] [rbp-B0h] BYREF
  int v127; // [rsp+54h] [rbp-ACh] BYREF
  _BYTE v128[8]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v129; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v130; // [rsp+68h] [rbp-98h] BYREF
  struct _MEMORYSTATUSEX v131; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v132[8]; // [rsp+B0h] [rbp-50h] BYREF
  _MEMORYSTATUSEX Buffer; // [rsp+130h] [rbp+30h] BYREF
  struct _MEMORYSTATUSEX v134; // [rsp+170h] [rbp+70h] BYREF
  struct _MEMORYSTATUSEX v135; // [rsp+1B0h] [rbp+B0h] BYREF
  struct _JOBOBJECT_EXTENDED_LIMIT_INFORMATION v136; // [rsp+1F0h] [rbp+F0h] BYREF
  struct _JOBOBJECT_EXTENDED_LIMIT_INFORMATION v137; // [rsp+280h] [rbp+180h] BYREF
  struct _PROCESS_MEMORY_COUNTERS_EX v138; // [rsp+310h] [rbp+210h] BYREF
  struct _PROCESS_MEMORY_COUNTERS_EX v139; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v140[4096]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v141[4096]; // [rsp+13B0h] [rbp+12B0h] BYREF
  char v142[1024]; // [rsp+23B0h] [rbp+22B0h] BYREF
  char v143[512]; // [rsp+27B0h] [rbp+26B0h] BYREF
  wchar_t v144[264]; // [rsp+29B0h] [rbp+28B0h] BYREF

  if ( FUseReplicatedServerContext() )
    v0 = (RESOURCE *)((char *)qword_10049F360 + 28520);
  else
    v0 = (RESOURCE *)((char *)qword_10049F360 + 14864);
  SysConfigPagePtr::Bootstrap(v0);
  v1 = *((_DWORD *)qword_10049F360 + 12127);
  v2 = (v1 & 1) == 0 && (v1 & 2) == 0 && !*((_DWORD *)qword_10049F360 + 3636);
  CommonGlobalState::m_CollectingStatistics = v2;
  if ( (*((_BYTE *)qword_10049F360 + 48508) & 2) != 0 )
  {
    SOS_Tracing::NotifyTraceOn(0x1F98u);
    SOS_Tracing::NotifyTraceOn(0x1F9Fu);
  }
  SOS_PublicGlobals::sm_NodeInit = (enum SOS_RESULT (__high *)(struct SOS_Node *const))&SOSNodeInitRoutine;
  SOS_PublicGlobals::sm_BootFinalize = (enum SOS_RESULT (__high *)(void))&SOSBootFinalizeRoutine;
  utgettime((struct SQLDATEBASE *)v128, 0, 0);
  CSysInfoTable::SetSOSStartTime((const struct SQLDATE *)v128);
  RefreshProcessAffinity();
  if ( FUseReplicatedServerContext() )
    v3 = (char *)qword_10049F360 + 28520;
  else
    v3 = (char *)qword_10049F360 + 14864;
  if ( v3[12366] )
  {
    CurrentProcess = GetCurrentProcess();
    if ( SetPriorityClass(CurrentProcess, 0x80u) )
    {
      CurrentThread = GetCurrentThread();
      if ( SetThreadPriority(CurrentThread, 2) )
        goto LABEL_24;
    }
    LastError = GetLastError();
    OSErrString = GetOSErrString(LastError, (struct ErrorStringHolder *)v140, 0, 0);
    scierrlog(0x429Du, L"StartUp::BoostPriority", OSErrString);
    v8 = 299;
LABEL_23:
    SQLExit(v8, 17053, 1066);
LABEL_24:
    PriorityClass = 128;
    goto LABEL_25;
  }
  v9 = GetCurrentProcess();
  PriorityClass = GetPriorityClass(v9);
  if ( PriorityClass == 256 && SOS_PublicGlobals::sm_cpuCount == 1 )
  {
    v11 = GetCurrentProcess();
    if ( SetPriorityClass(v11, PriorityClass - 128) )
    {
      v12 = GetCurrentThread();
      if ( SetThreadPriority(v12, 2) )
        goto LABEL_24;
    }
    v13 = GetLastError();
    v14 = GetOSErrString(v13, (struct ErrorStringHolder *)v141, 0, 0);
    scierrlog(0x429Du, L"StartUp::BoostPriority", v14);
    v8 = 40;
    goto LABEL_23;
  }
LABEL_25:
  v15 = 0;
  scierrlog((PriorityClass == 128) + 17162);
  Buffer.dwLength = 64;
  GlobalMemoryStatusEx(&Buffer);
  scierrlog(0xC2EFu, Buffer.ullTotalPhys >> 20);
  v16 = 0;
  if ( PriorityClass == 128 )
    v16 = 2;
  SOS_PublicGlobals::sm_Priority = v16;
  SOS_OS::SetUnhandledExceptionFilter();
  SOS_OS::SetInvalidParameterHandler();
  SOS_OS::SetAbortHandler();
  v17 = qword_10049F340;
  if ( (*(_BYTE *)(qword_10049F340 + 457) & 1) != 0 )
  {
    SOS_OS_StackBackTraceRoutine = DbgEngineStackBackTrace;
    v17 = qword_10049F340;
  }
  v18 = *((_DWORD *)s_pServerConf + 2);
  if ( (!v18 || v18 == 3 || *((_DWORD *)s_pServerConf + 3) == 2) && (*(_BYTE *)(v17 + 456) & 0x40) == 0 )
    SOS_PublicGlobals::sm_osOptions &= ~4u;
  if ( *((_DWORD *)qword_10049F360 + 3626) )
    SOS_PublicGlobals::sm_osOptions |= 8u;
  v19 = v142;
  v20 = 64;
  SOS_OS_CreateTraceBuffRoutine = (struct SOS_TraceStreamBuffer *(*)(struct IMemObj *))GetCerrStreamBuf;
  SOS_OS_ErrorLogRoutine = scierrlog;
  SOS_OS_LogUnlocalizedRoutine = SOSLogToErrorLog;
  SOS_PublicGlobals::sm_LogSystemMetadataRoutine = (void (*)(const wchar_t *, ...))LogSystemMetadataNotSentToClient;
  SOS_PublicGlobals::sm_DumpExceptionHandlerRoutine = (int (*)(struct _EXCEPTION_POINTERS *))SqlDumpExceptionHandler;
  SOS_OS_ExNotificationRoutine = ex_sqltrace_event;
  SOS_OS_ShouldStackDumpForErrorCallBack = (int (*)(unsigned int, int))FGenerateDumpForErrorWrapper;
  SOS_OS_StackTraceRoutine = (void (*)(void *, const wchar_t *, unsigned int, void **))stackTraceCallBack;
  SOS_OS_ExceptionPrintRoutine = (void (*)(int, int, int, char *))ex_vcallprint_no_dump_no_retval;
  SOS_OS_UserLogRoutine = user_log;
  SOS_OS_ExPreCallBackRoutine = ex_exception_precallback;
  SOS_OS_ExPostCallBackRoutine = ex_exception_postcallback;
  SOS_PublicGlobals::sm_OutOfMemoryHandlerRoutine = (int (*)(unsigned __int64))SQLFatalHandlers::OutOfMemoryHandlerRoutine;
  SOS_OS_DescribeResourceRoutine = (int (*)(unsigned int, unsigned __int8 *, unsigned int, wchar_t *, unsigned int *))SQLDescribeResourceRoutine;
  SOS_PublicGlobals::sm_ExitRoutine = (void (*)(unsigned int))SQLExitWrapper;
  SOS_OS_SymbolizeRoutine = SymbolizeFrames;
  SOS_OS_CriticalExceptionCheckRoutine = (void (*)(unsigned int))CmdLineParamProcessDash_g;
  SOS_OS_OverlappedResultRoutine = DBGetOverlappedResult;
  do
  {
    GroupAffinity::GroupAffinity((GroupAffinity *)v19);
    v19 += 16;
    --v20;
  }
  while ( v20 );
  v21 = qword_10049F360;
  v22 = 0;
  v121 = 0;
  if ( *((_DWORD *)qword_10049F360 + 3636) )
    goto LABEL_42;
  if ( !*((_DWORD *)qword_10049F360 + 3637) )
  {
    StartUp::ReadNodeConfiguration((struct GroupAffinity *const)v142, &v121);
    v22 = v121;
    v21 = qword_10049F360;
  }
  if ( *((_DWORD *)v21 + 3636) )
  {
LABEL_42:
    v121 = 0;
  }
  else if ( v22 )
  {
    SOS_OS::SetNodeConfiguration((struct GroupAffinity *)v142, v22);
  }
  v23 = FUseReplicatedServerContext();
  v24 = (char *)qword_10049F360 + 14864;
  if ( v23 )
    v24 = (char *)qword_10049F360 + 28520;
  v25 = 1;
  v26 = s_pServerConf;
  v27 = *((unsigned int *)s_pServerConf + 2);
  *((_DWORD *)qword_10049F360 + 13) = (_DWORD)v27
                                   && (_DWORD)v27 != 3
                                   && (*((_BYTE *)qword_10049F360 + 48508) & 0x20) == 0
                                   && ((v27 = qword_10049F340,
                                        v26 = (struct IServerConfiguration *)*(unsigned __int8 *)(qword_10049F340 + 201),
                                        ((unsigned __int8)v26 & 0x20) != 0)
                                    || *((_WORD *)v24 + 6223) && (char)v26 >= 0);
  if ( !*((_DWORD *)qword_10049F360 + 3626) )
  {
    if ( !v24[13639] && (*(_BYTE *)(qword_10049F340 + 1009) & 0x10) == 0 )
    {
      SOS_PublicGlobals::sm_osStatus |= 0x1000u;
      goto LABEL_64;
    }
    v30 = *(_DWORD **)&SOS_PublicGlobals::sm_osStatus;
    goto LABEL_63;
  }
  v28 = *(_BYTE *)(GetXdbServerGlobals(v27, v26) + 16290) == 0;
  v30 = *(_DWORD **)&SOS_PublicGlobals::sm_osStatus;
  if ( v28 )
  {
LABEL_63:
    *v30 &= ~0x1000u;
    goto LABEL_64;
  }
  SOS_PublicGlobals::sm_osStatus |= 0x1000u;
  if ( *(_DWORD *)(GetXdbServerGlobals(v27, v29) + 16292) )
  {
    XdbServerGlobals = GetXdbServerGlobals(v27, v31);
    v27 = *(unsigned int *)(XdbServerGlobals + 16292);
    SOS_OS_PhysicalCoresPerSoftNumaThreshold = *(_DWORD *)(XdbServerGlobals + 16292);
  }
LABEL_64:
  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    IsFeatureSwitchOn = HostReg_IsFeatureSwitchOn(L"SQL.Config", L"SmallMemoryEnvironment", 0);
    if ( *(int *)(GetXdbServerGlobals(v35, v34) + 19408) >= 0 )
    {
      v36 = (unsigned __int8)HostReg_IsFeatureSwitchOn(L"SQL.Config", L"SmallMemoryEnvironmentServerless", 0)
         && SOS_PublicGlobals::sm_cpuCount <= 8;
      IsFeatureSwitchOn |= v36;
      if ( IsFeatureSwitchOn )
        SOS_Tracing::NotifyTraceOn(0x1FBAu);
    }
  }
  else
  {
    IsFeatureSwitchOn = *(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance(v27) + 1420);
  }
  v37 = qword_10049F360;
  if ( (*((_BYTE *)qword_10049F360 + 48508) & 0x20) != 0 || IsFeatureSwitchOn )
  {
    log_unlocalized(L"Enabling small memory environment configuration.");
    SOS_PublicGlobals::sm_osStatus |= 0x10000u;
    v37 = qword_10049F360;
  }
  if ( (*((_BYTE *)v37 + 48508) & 0x20) != 0 )
  {
    CGlobalTraceFlags::TurnOn(8015, 0);
    CGlobalTraceFlags::TurnOff(834, 0);
    CGlobalTraceFlags::TurnOff(876, 0);
    CGlobalTraceFlags::NotifyTraceOff(0x36Cu);
  }
  memset(&v131, 0, sizeof(v131));
  v131.dwLength = 64;
  GlobalMemoryStatusEx(&v131);
  if ( (*(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance(v38) + 956) || (*(_BYTE *)(qword_10049F340 + 109) & 0x10) != 0)
    && (!*((_DWORD *)qword_10049F360 + 3626) && *((_DWORD *)s_pServerConf + 2) != 2 || v131.ullTotalPhys < 0x200000000LL) )
  {
    CGlobalTraceFlags::TurnOff(876, 0);
    CGlobalTraceFlags::NotifyTraceOff(0x36Cu);
    if ( *((_DWORD *)s_pServerConf + 2) == 2 )
      scierrlog(0x855Au, L"and/use large allocations.");
    else
      scierrlog(
        0x216u,
        34,
        L"Large allocations",
        *((unsigned int *)qword_10049F360 + 2934),
        *((_QWORD *)qword_10049F360 + 1466));
  }
  if ( *((_DWORD *)s_pServerConf + 2) == 2 && MemoryNode_LargePageSize )
  {
    if ( v131.ullTotalPhys >= 0x200000000LL )
    {
      SOS_PublicGlobals::sm_osStatus |= 0x10u;
    }
    else if ( (*(_BYTE *)(qword_10049F340 + 104) & 4) != 0 )
    {
      CGlobalTraceFlags::TurnOff(834, 0);
      scierrlog(0x855Au, L"and/use large pages.");
    }
  }
  else if ( (*(_BYTE *)(qword_10049F340 + 104) & 4) != 0 )
  {
    CGlobalTraceFlags::TurnOff(834, 0);
    if ( *((_DWORD *)s_pServerConf + 2) == 2 )
      log_unlocalized(L"Cannot use large pages in the memory manager!");
    else
      scierrlog(
        0x216u,
        22,
        L"Large pages",
        *((unsigned int *)qword_10049F360 + 2934),
        *((_QWORD *)qword_10049F360 + 1466));
  }
  if ( (*(_BYTE *)(qword_10049F340 + 104) & 4) != 0 )
  {
    CGlobalTraceFlags::TurnOn(876, 0);
    CGlobalTraceFlags::NotifyTraceOn(0x36Cu);
  }
  v39 = 3;
  IsAWE_SKU = SysConfigPagePtr::IsAWE_SKU();
  if ( *((_DWORD *)s_pServerConf + 2) == 2
    && (*(_BYTE *)(qword_10049F340 + 104) & 4) != 0
    && (SOS_PublicGlobals::sm_osStatus & 0x10) != 0 )
  {
    v41 = 1;
    SOS_OS_ExtraMemToLeaveBytes = GetBPoolOverheadBytes();
    scierrlog(0x350u);
  }
  else if ( (*(_BYTE *)(qword_10049F340 + 109) & 0x40) != 0 )
  {
    v41 = 4;
    SOS_OS_SharedMemoryContextExternalFragmentCount = 1;
    scierrlog(0x5Cu);
  }
  else if ( (SOS_PublicGlobals::sm_osStatus & 0x800) == 0
         || (*(_BYTE *)(qword_10049F340 + 104) & 8) != 0
         || OsInfo::IsXPlatInstance(SOS_OS_OsInfo)
         || !IsAWE_SKU )
  {
    v41 = 3;
    scierrlog(0x354u);
  }
  else
  {
    v41 = 2;
    scierrlog(0x351u);
  }
  SOS_OS_MemoryModel = v41;
  if ( (*(_BYTE *)(qword_10049F340 + 101) & 8) != 0 )
    SOS_PublicGlobals::sm_osStatus |= 0x2000u;
  SOS_PublicGlobals::sm_NodeLsSize = 12;
  SOS_PublicGlobals::sm_SchedLsSize = 8;
  *((_DWORD *)&SOS_PublicGlobals::sm_ResourceManager + 3) = 4;
  *((_DWORD *)&SOS_PublicGlobals::sm_ResourceManager + 4) = 2;
  *((_QWORD *)&SOS_PublicGlobals::sm_ResourceManager + 3) = FEqWszHostDefault;
  *((_QWORD *)&SOS_PublicGlobals::sm_ResourceManager + 4) = IHashWHostDefault;
  *(_QWORD *)SOS_IOResourceManager::GetManager() = FCB::IssuePendingIO;
  *(_QWORD *)(SOS_IOResourceManager::GetManager() + 8) = FCB::OnThrottlePendingIO;
  SOS_OS::SetMaxWorkersLowerBoundViolatedCallbackRoutine((void (*)(void))SQL_SOSMaxWorkersLowerBoundViolatedCallbackRoutine);
  v43 = 900000;
  v44 = ~(unsigned __int8)(*((_DWORD *)qword_10049F360 + 12127) >> 11) & 4 | 3u;
  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    if ( (SOS_PublicGlobals::sm_osStatus & 0x20) != 0 )
      v39 = ~(unsigned __int8)(*((_DWORD *)qword_10049F360 + 12127) >> 11) & 4 | 3;
    SOS_OS_MaxWorkersPerSchedulerLowerBound = v39;
    v45 = GetXdbServerGlobals(v44, v42);
    SOS_OS::ConfigureMaxWorkers(*(_DWORD *)(v45 + 16552));
    v47 = *(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance(v46) + 139);
    v52 = *(int *)(GetXdbServerGlobals(v49, v48) + 16564);
    v53 = (unsigned __int64 *)SOS_OS_MinSosGapWithJobMemLimitInBytes;
    v54 = v52 << 20;
    if ( v47 )
    {
      v54 += GetMemorySavingsInBytes();
      v53 = (unsigned __int64 *)SOS_OS_MinSosGapWithJobMemLimitInBytes;
    }
    if ( v54 >= SOS_OS_MinSosGapWithJobMemLimitInBytes )
    {
      v55 = v54;
      if ( v54 == -1 )
        v55 = *v53;
      MemoryNode::GetGlobalMemoryStatus(&v134, &v138, &v136, &v126, &v129);
      v56 = v136.ProcessMemoryLimit >> 13;
      if ( (SOS_OS_JobLowMemorySignalThresholdBytes >> 13) + (v55 >> 13) + MemoryNode::GetTotalPagesCommitted() >= v56 )
      {
LABEL_123:
        v59 = *(int *)(GetXdbServerGlobals(v51, v50) + 16568);
        v60 = (unsigned __int64 *)SOS_OS_JobLowMemorySignalThresholdBytes;
        v61 = v59 << 20;
        if ( v61 >= SOS_OS_JobLowMemorySignalThresholdBytes )
        {
          MemoryNode::GetGlobalMemoryStatus(&v135, &v139, &v137, &v127, &v130);
          v62 = v137.ProcessMemoryLimit >> 13;
          TotalPagesCommitted = MemoryNode::GetTotalPagesCommitted();
          v58 = v61 >> 13;
          if ( (v61 >> 13) + (SOS_OS_MinSosGapWithJobMemLimitInBytes >> 13) + TotalPagesCommitted >= v62 )
          {
LABEL_127:
            SOS_OS_MinHealthyRateOfMemReleaseKB = *(int *)(GetXdbServerGlobals(v58, v57) + 16572);
            v65 = GetXdbServerGlobals(SOS_OS_MinHealthyRateOfMemReleaseKB, v64);
            v66 = *(unsigned __int8 *)(v65 + 16925);
            SOS_OS_IgnoreNonYieldingScheduler = *(unsigned __int8 *)(v65 + 16925);
            v43 = 1000 * *(_DWORD *)(GetXdbServerGlobals(v66, v67) + 16576);
            goto LABEL_130;
          }
          v60 = (unsigned __int64 *)SOS_OS_JobLowMemorySignalThresholdBytes;
        }
        *v60 = v61;
        goto LABEL_127;
      }
      v53 = (unsigned __int64 *)SOS_OS_MinSosGapWithJobMemLimitInBytes;
    }
    *v53 = v54;
    goto LABEL_123;
  }
  SOS_OS_MaxWorkersPerSchedulerLowerBound = ~(unsigned __int8)(*((_DWORD *)qword_10049F360 + 12127) >> 11) & 4 | 3;
  if ( !(unsigned int)SOS_OS::ConfigureMaxWorkers(*((unsigned __int16 *)v24 + 6236)) )
    scierrlog(0xC2EDu, *((unsigned __int16 *)v24 + 6236), SOS_PublicGlobals::sm_MaxWorkers);
LABEL_130:
  v122 = 1;
  SOS_PublicGlobals::sm_MinPooledWorkers = 1;
  if ( (*((_BYTE *)&SOS_PublicGlobals::sm_traceFlags + 188) & 0x20) != 0 )
    v43 = 300000;
  SOS_PublicGlobals::sm_IdleTimeOut = v43;
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
    v68 = (Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart * (unsigned __int64)v43 + 999) / 0x3E8;
  else
    v68 = 10000LL * v43;
  SOS_PublicGlobals::sm_IdleTimeOutTicks = v68;
  SOS_PublicGlobals::sm_IdleOfflineTimeOut = 120000;
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
    v69 = (Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart
         * (unsigned __int64)SOS_PublicGlobals::sm_IdleOfflineTimeOut
         + 999)
        / 0x3E8;
  else
    v69 = 10000LL * SOS_PublicGlobals::sm_IdleOfflineTimeOut;
  SOS_PublicGlobals::sm_IdleOfflineTimeOutTicks = v69;
  v70 = *((_DWORD *)qword_10049F360 + 13) == 0;
  SOS_PublicGlobals::sm_WorkerType = *((_DWORD *)qword_10049F360 + 13) == 0;
  if ( *((_BYTE *)&g_featureSwitchesDk + 93) && (*(_BYTE *)(qword_10049F340 + 1012) & 0x10) == 0 )
    SOS_PublicGlobals::sm_SpinCounter = 5400;
  if ( *(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance(v70) + 1366) )
  {
    v72 = 174;
    v73 = 10;
    do
    {
      v74 = __rdtsc();
      _mm_pause();
      v75 = __rdtsc();
      v76 = (((unsigned __int64)HIDWORD(v75) << 32) | (unsigned int)v75) - v74;
      if ( v76 >= v72 )
        v76 = v72;
      v72 = v76;
      --v73;
    }
    while ( v73 );
    v77 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
    if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
      v77 = SOS_OS_LogUnlocalizedRoutine;
    v77(L"Detected pause instruction latency: %u cycles.\n", v76);
    if ( v72 <= 0x28 )
    {
      SOS_PublicGlobals::sm_SpinIncrement = 1;
    }
    else
    {
      SOS_PublicGlobals::sm_SpinIncrement = v72 / 0x28;
      v78 = (void (*)(const wchar_t *, ...))SOS_PublicGlobals::sm_LogSystemMetadataRoutine;
      if ( !SOS_PublicGlobals::sm_LogSystemMetadataRoutine )
        v78 = SOS_OS_LogUnlocalizedRoutine;
      v78(L"Spin divider value used: %u\n", SOS_PublicGlobals::sm_SpinIncrement);
    }
  }
  if ( *(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance(v71) + 1440)
    || (*(_BYTE *)(qword_10049F340 + 1012) & 0x40) != 0 )
  {
    SOS_PublicGlobals::sm_StaggerEnabledForSpinToAcquire = 1;
  }
  if ( *(_BYTE *)(CFeatureSwitchesMin::GetCurrentInstance(v79) + 1438) )
    SOS_PublicGlobals::sm_SpinlockStatSnapshot = 1;
  SOS_PublicGlobals::sm_SwitchCallBackRoutine = (void (*)(struct SOS_Task *, int))switch_call_back;
  SOS_OS::SetRaiseExecutionAbortedErrorCallbackRoutine((void (__high *)(enum ABORT_AND_LCK_EXCEPTIONS))&RaiseExecutionAbortedError);
  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  SOS_OS_HeapQueryInformationRoutine = (int (*)(void *, enum _HEAP_INFORMATION_CLASS, void *, unsigned __int64, unsigned __int64 *))GetProcAddress(ModuleHandleW, "HeapQueryInformation");
  qword_1004D28B8 = (__int64)SQL_SOSGetSPidAndRequestId;
  qword_1004A9A00 = *((_QWORD *)&SOS_PublicGlobals::sm_SetAbortCallbackList + 1);
  **((_QWORD **)&SOS_PublicGlobals::sm_SetAbortCallbackList + 1) = &g_ClrSetAbortCallback;
  *((_QWORD *)&SOS_PublicGlobals::sm_SetAbortCallbackList + 1) = &g_ClrSetAbortCallback;
  g_ClrSetAbortCallback = SOS_PublicGlobals::sm_SetAbortCallbackList;
  qword_1004A0940 = *((_QWORD *)&SOS_PublicGlobals::sm_NonYieldSchedulerCallbackList + 1);
  **((_QWORD **)&SOS_PublicGlobals::sm_NonYieldSchedulerCallbackList + 1) = &g_SchedMonitorCallback;
  *((_QWORD *)&SOS_PublicGlobals::sm_NonYieldSchedulerCallbackList + 1) = &g_SchedMonitorCallback;
  g_SchedMonitorCallback = SOS_PublicGlobals::sm_NonYieldSchedulerCallbackList;
  qword_1004A0958 = *((_QWORD *)&SOS_PublicGlobals::sm_DeadlockSchedulerCallbackList + 1);
  **((_QWORD **)&SOS_PublicGlobals::sm_DeadlockSchedulerCallbackList + 1) = &g_DeadlockSchedulerCallback;
  *((_QWORD *)&SOS_PublicGlobals::sm_DeadlockSchedulerCallbackList + 1) = &g_DeadlockSchedulerCallback;
  g_DeadlockSchedulerCallback = SOS_PublicGlobals::sm_DeadlockSchedulerCallbackList;
  qword_1004A0970 = *((_QWORD *)&SOS_PublicGlobals::sm_NonYieldIOCPCallbackList + 1);
  **((_QWORD **)&SOS_PublicGlobals::sm_NonYieldIOCPCallbackList + 1) = &g_NonYieldIOCPCallback;
  *((_QWORD *)&SOS_PublicGlobals::sm_NonYieldIOCPCallbackList + 1) = &g_NonYieldIOCPCallback;
  g_NonYieldIOCPCallback = SOS_PublicGlobals::sm_NonYieldIOCPCallbackList;
  qword_1004A0988 = *((_QWORD *)&SOS_PublicGlobals::sm_IdleServerCheckCallbackList + 1);
  **((_QWORD **)&SOS_PublicGlobals::sm_IdleServerCheckCallbackList + 1) = &g_IdleServerCheckCallback;
  *((_QWORD *)&SOS_PublicGlobals::sm_IdleServerCheckCallbackList + 1) = &g_IdleServerCheckCallback;
  g_IdleServerCheckCallback = SOS_PublicGlobals::sm_IdleServerCheckCallbackList;
  qword_1004D26F0 = *((_QWORD *)&SOS_PublicGlobals::sm_IdleServerCheckCallbackList + 1);
  **((_QWORD **)&SOS_PublicGlobals::sm_IdleServerCheckCallbackList + 1) = &g_IdleFsAgentCheckCallback;
  *((_QWORD *)&SOS_PublicGlobals::sm_IdleServerCheckCallbackList + 1) = &g_IdleFsAgentCheckCallback;
  g_IdleFsAgentCheckCallback = SOS_PublicGlobals::sm_IdleServerCheckCallbackList;
  qword_10049F7B8 = *((_QWORD *)&SOS_PublicGlobals::sm_MemUtilizationEffectCallbackList + 1);
  **((_QWORD **)&SOS_PublicGlobals::sm_MemUtilizationEffectCallbackList + 1) = &g_MemUtilizationEffectCallback;
  *((_QWORD *)&SOS_PublicGlobals::sm_MemUtilizationEffectCallbackList + 1) = &g_MemUtilizationEffectCallback;
  g_MemUtilizationEffectCallback = SOS_PublicGlobals::sm_MemUtilizationEffectCallbackList;
  qword_1004A09A8 = *((_QWORD *)&SOS_PublicGlobals::sm_NonYieldRMCallbackList + 1);
  **((_QWORD **)&SOS_PublicGlobals::sm_NonYieldRMCallbackList + 1) = &g_NonYieldRMCallback;
  *((_QWORD *)&SOS_PublicGlobals::sm_NonYieldRMCallbackList + 1) = &g_NonYieldRMCallback;
  g_NonYieldRMCallback = SOS_PublicGlobals::sm_NonYieldRMCallbackList;
  SOS_OS::AddExternalMonitorCallback(&g_ExternalMonitorCallback);
  qword_1004A09D8 = *((_QWORD *)&SOS_PublicGlobals::sm_IdleServerEventCallbackList + 1);
  **((_QWORD **)&SOS_PublicGlobals::sm_IdleServerEventCallbackList + 1) = &g_IdleServerEventCallback;
  *((_QWORD *)&SOS_PublicGlobals::sm_IdleServerEventCallbackList + 1) = &g_IdleServerEventCallback;
  g_IdleServerEventCallback = SOS_PublicGlobals::sm_IdleServerEventCallbackList;
  SOS_OS::AddStuckDispatcherCallback(&g_StuckDispatcherCallback);
  SOS_OS::AddStuckDispatcherCallback(&g_StuckLoginDispatcherCallback);
  qword_1004D2040 = *((_QWORD *)&SOS_PublicGlobals::sm_NonYieldSchedulerCallbackList + 1);
  **((_QWORD **)&SOS_PublicGlobals::sm_NonYieldSchedulerCallbackList + 1) = &g_ClrNonYieldSchedulerCallback;
  *((_QWORD *)&SOS_PublicGlobals::sm_NonYieldSchedulerCallbackList + 1) = &g_ClrNonYieldSchedulerCallback;
  g_ClrNonYieldSchedulerCallback = SOS_PublicGlobals::sm_NonYieldSchedulerCallbackList;
  SOS_OS_ResourceMonitorRoutine = (void *(*)(void *))SetupResourceMonitorTaskContext;
  if ( *((_DWORD *)qword_10049F360 + 3636)
    || (v81 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf
                                                                                        + 224LL))(s_pServerConf),
        (*(_BYTE *)(qword_10049F340 + 501) & 4) != 0)
    || ((v82 = *((_DWORD *)s_pServerConf + 2)) == 0
     || v82 == 3
     || *((_DWORD *)qword_10049F360 + 3637)
     || *((_DWORD *)s_pServerConf + 3) == 1)
    && (*(_BYTE *)(qword_10049F340 + 975) & 0x40) == 0
    || !IsDACAvailable(v81) )
  {
    SOS_PublicGlobals::sm_osStatus &= ~8u;
  }
  else
  {
    v83 = (char *)qword_10049F360 + 44300;
    v125 = 0;
    DefaultLocale = GetDefaultLocale();
    v85 = StringCchPrintf_lW(v144, 0x105u, L"%ls", DefaultLocale, v83);
    v86 = v85;
    if ( v85 < 0 )
    {
      _mm_lfence();
      SetWin32ExitCode(v85);
      v87 = GetDefaultLocale();
      v88 = StringCchPrintf_lA(v143, 0x200u, "%hs (HRESULT 0x%x)", v87, "String Format Failure (DAC keystring)", v86);
      v89 = "String Format Failure (DAC keystring)";
      if ( v88 >= 0 )
        v89 = v143;
      FailAndExit(v89);
    }
    if ( !(unsigned int)IniRegOpenKeyExW(-2147483646, (int)v144, 0, 1, &v125) )
    {
      v123 = 4;
      if ( !(unsigned int)IniRegQueryValueExW((int)v125, (int)L"NumDACCount", 0, 0, v124, &v123) )
        SOS_OS_NumDACCount = *(_DWORD *)v124;
      IniRegCloseKey(v125);
    }
  }
  if ( v24[12551] == 1 )
  {
    SOS_PublicGlobals::sm_CommonCriteriaModeEnabled = 1;
    scierrlog(0x42D2u);
  }
  if ( *((_DWORD *)qword_10049F360 + 3645) )
  {
    v90 = (*(__int64 (__fastcall **)(struct IServerConfiguration *, __int64))(*(_QWORD *)s_pServerConf + 432LL))(
            s_pServerConf,
            60);
    v91 = (*(__int64 (__fastcall **)(struct IServerConfiguration *, __int64))(*(_QWORD *)s_pServerConf + 440LL))(
            s_pServerConf,
            120);
    dword_1004A08D0 = 5000 * ((1000 * v90 + 4999) / 0x1388);
    dword_1004A08D4 = 10000 * ((1000 * v91 + 9999) / 0x2710);
    log_unlocalized(L"Orca: SOSNonYieldSchedulerErrorPeriodInSec=%d.", v90);
    log_unlocalized(L"Orca: SOSNonYieldSchedulerDumpPeriodInSec=%d.", v91);
  }
  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    if ( (unsigned __int8)HostReg_IsFeatureSwitchOn(L"SQL.Config", L"YukonRtmCacheLimits", 0) )
    {
      CGlobalTraceFlags::TurnOn(8032, 0);
      LogSystemMetadataNotSentToClient(L"Trace flag %d is ON. Use Yukon RTM cache limits.\n", 8032);
    }
    if ( !(unsigned __int8)HostReg_IsFeatureSwitchOn(L"SQL.Config", L"WorkerStealing", 0) )
    {
      CGlobalTraceFlags::TurnOn(8094, 0);
      LogSystemMetadataNotSentToClient(L"Trace flag %d is ON. Disable WorkerStealing.\n", 8094);
    }
    if ( (unsigned __int8)HostReg_IsFeatureSwitchOn(L"SQL.Config", L"TaskPreallocation", 0) )
    {
      CGlobalTraceFlags::TurnOn(8114, 0);
      LogSystemMetadataNotSentToClient(L"Trace flag %d is ON. Enable SOS task preallocation.\n", 8114);
    }
    if ( (unsigned __int8)HostReg_IsFeatureSwitchOn(L"SQL.Config", L"CPUStarvationStats", 0) )
    {
      CGlobalTraceFlags::TurnOn(8123, 0);
      LogSystemMetadataNotSentToClient(L"Trace flag %d is ON. Enable CPU starvation stats.\n", 8123);
    }
    if ( (unsigned __int8)HostReg_IsFeatureSwitchOn(L"SQL.Config", L"CPUQuantumThiefStats", 0) )
    {
      CGlobalTraceFlags::TurnOn(8127, 0);
      LogSystemMetadataNotSentToClient(L"Trace flag %d is ON. Enable quantum thief stats.\n", 8127);
    }
    if ( (unsigned __int8)HostReg_IsFeatureSwitchOn(L"SQL.Config", L"TraceMemAllocFreeInPmo", 0) )
    {
      CGlobalTraceFlags::TurnOn(8109, 0);
      LogSystemMetadataNotSentToClient(L"Trace flag %d is ON. Enable memobj ring buffer.\n", 8109);
    }
    if ( !(unsigned __int8)HostReg_IsFeatureSwitchOn(L"SQL.Config", L"MemImprovements", 0) )
    {
      CGlobalTraceFlags::TurnOn(8125, 0);
      LogSystemMetadataNotSentToClient(L"Trace flag %d is ON. Disable memory manager improvements.\n", 8125);
    }
  }
  v92 = qword_10049F340;
  if ( (*(_BYTE *)(qword_10049F340 + 1004) & 1) != 0 )
  {
    SOS_OS::SetCachesAlternativeMemoryLimits();
    v92 = qword_10049F340;
  }
  if ( !*((_DWORD *)qword_10049F360 + 13)
    && (*((_DWORD *)qword_10049F360 + 12127) & 0x2000) == 0
    && (*(_BYTE *)(v92 + 1006) & 8) == 0 )
  {
    v93 = GetCurrentProcess();
    SetProcessPriorityBoost(v93, 1);
  }
  v94 = *((_DWORD *)qword_10049F360 + 12127);
  if ( (v94 & 0x21) != 0 && (v94 & 0x2000) == 0 )
    CGlobalTraceFlags::TurnOn(8040, 0);
  if ( !*((_DWORD *)qword_10049F360 + 3636) && *((_DWORD *)s_pServerConf + 2) != 2 )
    *((_DWORD *)&SOS_PublicGlobals::sm_ResourceManager + 26) &= ~1u;
  SOS_OS_VetoableCpuChangeRoutine = (struct SystemAffinity (__high *)(struct SystemAffinity, struct SystemAffinity))StartUp::VetoableCpuChangeCallback;
  SOS_PublicGlobals::sm_IsHotAddCpuSupportEnabled = *((_DWORD *)s_pServerConf + 2) == 2;
  if ( *((_DWORD *)s_pServerConf + 2) != 1
    || !(unsigned int)HwInfo::GetVirtualMachineType()
    || (v95 = 1, (SOS_PublicGlobals::sm_osStatus & 0x4000) != 0) )
  {
    v95 = 0;
  }
  if ( OsInfo::IsXPlatInstance(SOS_OS_OsInfo) || *((_DWORD *)s_pServerConf + 2) != 2 && !v95 )
    v25 = 0;
  SOS_PublicGlobals::sm_IsHotAddMemorySupportEnabled = v25;
  v96 = *(_DWORD **)&SOS_PublicGlobals::sm_osOptions;
  if ( (SOS_PublicGlobals::sm_osOptions & 0x100) != 0 )
  {
    if ( !SOS_OS::IsHotAddCpuSupported(0) )
    {
      log_unlocalized(L"Warning: Machine does not support deferred scheduler allocation.");
      SOS_PublicGlobals::sm_osOptions &= ~0x100u;
    }
    v96 = *(_DWORD **)&SOS_PublicGlobals::sm_osOptions;
  }
  v97 = *((_DWORD *)s_pServerConf + 2);
  if ( v97 == 3 || !v97 )
    *v96 &= ~1u;
  v98 = SOS_OS::CheckHardwareCompatibility();
  if ( v98 )
  {
    if ( v98 == 1 )
      scierrlog(0x4333u);
    SQLExit(45);
  }
  GlobalBufferPool = GetGlobalBufferPool();
  BPool::ReadConfig(GlobalBufferPool);
  if ( !*((_DWORD *)qword_10049F360 + 3626) && (unsigned __int64)MemoryNode_MaxMemoryPagesLimit < 0x40000 )
    SOS_PublicGlobals::sm_osStatus |= 0x10000u;
  v120 = 0;
  ModuleHandleA = GetModuleHandleA(0);
  SOS_OS::IsLargePage(ModuleHandleA, &v120);
  if ( v120 )
  {
    scierrlog(0x42F3u, L"sqlservr.exe");
    v120 = 0;
    v101 = GetModuleHandleW(L"sqlmin.dll");
    SOS_OS::IsLargePage(v101, &v120);
    if ( v120 )
      scierrlog(0x42F3u, L"sqlmin.dll");
    v120 = 0;
    v102 = GetModuleHandleW(L"sqldk.dll");
    SOS_OS::IsLargePage(v102, &v120);
    if ( v120 )
      scierrlog(0x42F3u, L"sqldk.dll");
    v120 = 0;
    v103 = GetModuleHandleW(L"sqllang.dll");
    SOS_OS::IsLargePage(v103, &v120);
    if ( v120 )
      scierrlog(0x42F3u, L"sqllang.dll");
    v120 = 0;
    v104 = GetModuleHandleW(L"sqltses.dll");
    SOS_OS::IsLargePage(v104, &v120);
    if ( v120 )
      scierrlog(0x42F3u, L"sqltses.dll");
  }
  if ( *((_DWORD *)qword_10049F360 + 13) )
    scierrlog(0x42E4u);
  v105 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v106 = *(_QWORD *)(v105 + 256);
  *(_QWORD *)(v105 + 8) = 0;
  *(_QWORD *)(*(_QWORD *)(v106 + 64) + 8LL) = 0;
  v107 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v108 = *(_QWORD *)(v107 + 256);
  if ( !v108 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v108 = *(_QWORD *)(v107 + 256);
  }
  SOS_Task::GetLock(*(SOS_Task **)(v108 + 600));
  v109 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v110 = *(_QWORD *)(v109 + 256);
  *(_QWORD *)(v109 + 24) = 0;
  *(_QWORD *)(*(_QWORD *)(v110 + 64) + 24LL) = 0;
  v111 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v112 = *(_QWORD *)(v111 + 256);
  if ( !v112 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v112 = *(_QWORD *)(v111 + 256);
  }
  v113 = *(_QWORD *)(v112 + 600);
  if ( SOS_PublicGlobals::sm_SpinlockStatSnapshot )
  {
    v114 = rand();
    if ( v114 == 5 * (v114 / 5) )
      Spinlock<11,2,268435714>::UpdateStatSnapshot();
  }
  *(_QWORD *)(v113 + 144) = 0;
  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    *((_DWORD *)&SOS_PublicGlobals::sm_ResourceManager + 26) &= ~4u;
    *((_DWORD *)&SOS_PublicGlobals::sm_ResourceManager + 26) |= 0x10u;
    LOBYTE(v15) = SOS_OS::GetCPUCorePercentCap() < 100.0;
    if ( v15 )
    {
      CPUCorePercentCap = SOS_OS::GetCPUCorePercentCap();
      SOS_OS_WorkerHighUtilizationThreshold = (int)(CPUCorePercentCap * 40.0 / 100.0);
      SOS_OS_ProcessStarvedUtilizationThreshold = (int)(CPUCorePercentCap * 25.0 / 100.0);
      v132[0] = SOS_PublicGlobals::sm_osSystemAffinity[0];
      v132[1] = SOS_PublicGlobals::sm_osSystemAffinity[1];
      v132[2] = SOS_PublicGlobals::sm_osSystemAffinity[2];
      v132[3] = SOS_PublicGlobals::sm_osSystemAffinity[3];
      v132[4] = SOS_PublicGlobals::sm_osSystemAffinity[4];
      v132[5] = SOS_PublicGlobals::sm_osSystemAffinity[5];
      v132[6] = SOS_PublicGlobals::sm_osSystemAffinity[6];
      v132[7] = SOS_PublicGlobals::sm_osSystemAffinity[7];
      CPUCount = SystemAffinity::GetCPUCount((SystemAffinity *)v132);
      v119 = GetXdbServerGlobals(v118, v117);
      LogSystemMetadataNotSentToClient(
        L"SOS_OS::GetCPUCorePercentCap (): %f, GetXdbServerGlobals ()->corePercent: %f, SOS_OS::GetOsSystemAffinity ().Get"
         "CPUCount () = %d\n",
        CPUCorePercentCap,
        *(_QWORD *)(v119 + 24248),
        CPUCount);
    }
  }
}

```

## disassembly

```asm
0x100413d90  push    rbp
0x100413d92  push    rbx
0x100413d93  push    rsi
0x100413d94  lea     rbp, [rsp-2B00h]
0x100413d9c  mov     eax, 2C00h
0x100413da1  call    _alloca_probe
0x100413da6  sub     rsp, rax
0x100413da9  mov     rax, cs:__security_cookie
0x100413db0  xor     rax, rsp
0x100413db3  mov     [rbp+2B10h+var_50], rax
0x100413dba  mov     [rsp+2C10h+arg_0], rdi
0x100413dc2  mov     [rsp+2C10h+arg_8], r12
0x100413dca  mov     [rsp+2C10h+var_18], r14
0x100413dd2  mov     [rsp+2C10h+var_20], r15
0x100413dda  call    cs:__imp_?FUseReplicatedServerContext@@YA_NXZ; FUseReplicatedServerContext(void)
0x100413de0  mov     rcx, cs:qword_10049F360
0x100413de7  test    al, al
0x100413de9  jnz     short loc_100413DF4
0x100413deb  add     rcx, 3A10h
0x100413df2  jmp     short loc_100413DFB
0x100413df4  add     rcx, 6F68h
0x100413dfb  call    cs:__imp_?Bootstrap@SysConfigPagePtr@@QEAAXXZ; SysConfigPagePtr::Bootstrap(void)
0x100413e01  mov     rax, cs:qword_10049F360
0x100413e08  mov     ecx, [rax+0BD7Ch]
0x100413e0e  test    cl, 1
0x100413e11  jnz     short loc_100413E25
0x100413e13  test    cl, 2
0x100413e16  jnz     short loc_100413E25
0x100413e18  cmp     dword ptr [rax+38D0h], 0
0x100413e1f  jnz     short loc_100413E25
0x100413e21  mov     cl, 1
0x100413e23  jmp     short loc_100413E27
0x100413e25  xor     cl, cl
0x100413e27  mov     rax, cs:__imp_?m_CollectingStatistics@CommonGlobalState@@2_NA; bool CommonGlobalState::m_CollectingStatistics
0x100413e2e  mov     [rax], cl
0x100413e30  mov     rax, cs:qword_10049F360
0x100413e37  test    byte ptr [rax+0BD7Ch], 2
0x100413e3e  jz      short loc_100413E56
0x100413e40  mov     ecx, 1F98h
0x100413e45  call    cs:__imp_?NotifyTraceOn@SOS_Tracing@@SAXK@Z; SOS_Tracing::NotifyTraceOn(ulong)
0x100413e4b  mov     ecx, 1F9Fh
0x100413e50  call    cs:__imp_?NotifyTraceOn@SOS_Tracing@@SAXK@Z; SOS_Tracing::NotifyTraceOn(ulong)
0x100413e56  mov     rax, cs:__imp_?sm_NodeInit@SOS_PublicGlobals@@2P6A?AW4SOS_RESULT@@QEAVSOS_Node@@@ZEA; SOS_RESULT (*SOS_PublicGlobals::sm_NodeInit)(SOS_Node * const)
0x100413e5d  lea     rcx, ?SOSNodeInitRoutine@@YA?AW4SOS_RESULT@@QEAVSOS_Node@@@Z; SOSNodeInitRoutine(SOS_Node * const)
0x100413e64  xor     r8d, r8d
0x100413e67  xor     edx, edx
0x100413e69  mov     [rax], rcx
0x100413e6c  lea     rcx, ?SOSBootFinalizeRoutine@@YA?AW4SOS_RESULT@@XZ; SOSBootFinalizeRoutine(void)
0x100413e73  mov     rax, cs:__imp_?sm_BootFinalize@SOS_PublicGlobals@@2P6A?AW4SOS_RESULT@@XZEA; SOS_RESULT (*SOS_PublicGlobals::sm_BootFinalize)(void)
0x100413e7a  mov     [rax], rcx
0x100413e7d  lea     rcx, [rsp+2C10h+var_2BB8]
0x100413e82  call    cs:__imp_?utgettime@@YAXPEAUSQLDATEBASE@@HPEA_N@Z; utgettime(SQLDATEBASE *,int,bool *)
0x100413e88  lea     rcx, [rsp+2C10h+var_2BB8]
0x100413e8d  call    cs:__imp_?SetSOSStartTime@CSysInfoTable@@SAXAEBUSQLDATE@@@Z; CSysInfoTable::SetSOSStartTime(SQLDATE const &)
0x100413e93  call    ?RefreshProcessAffinity@@YAXXZ; RefreshProcessAffinity(void)
0x100413e98  call    cs:__imp_?FUseReplicatedServerContext@@YA_NXZ; FUseReplicatedServerContext(void)
0x100413e9e  test    al, al
0x100413ea0  mov     rax, cs:qword_10049F360
0x100413ea7  jnz     short loc_100413EB1
0x100413ea9  add     rax, 3A10h
0x100413eaf  jmp     short loc_100413EB7
0x100413eb1  add     rax, 6F68h
0x100413eb7  cmp     byte ptr [rax+304Eh], 0
0x100413ebe  mov     r15d, 2
0x100413ec4  jz      short loc_100413F30
0x100413ec6  call    cs:__imp_GetCurrentProcess
0x100413ecc  mov     rcx, rax; hProcess
0x100413ecf  lea     edx, [r15+7Eh]; dwPriorityClass
0x100413ed3  call    cs:__imp_SetPriorityClass
0x100413ed9  test    eax, eax
0x100413edb  jz      short loc_100413EF7
0x100413edd  call    cs:__imp_GetCurrentThread
0x100413ee3  mov     rcx, rax; hThread
0x100413ee6  mov     edx, r15d; nPriority
0x100413ee9  call    cs:__imp_SetThreadPriority
0x100413eef  test    eax, eax
0x100413ef1  jnz     loc_100413FCB
0x100413ef7  call    cs:__imp_GetLastError
0x100413efd  xor     r9d, r9d
0x100413f00  lea     rdx, [rbp+2B10h+var_2860]
0x100413f07  mov     ecx, eax
0x100413f09  xor     r8d, r8d
0x100413f0c  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x100413f12  lea     rdx, aStartupBoostpr; "StartUp::BoostPriority"
0x100413f19  mov     ecx, 429Dh; unsigned int
0x100413f1e  mov     r8, rax
0x100413f21  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100413f26  mov     ecx, 12Bh
0x100413f2b  jmp     loc_100413FBA
0x100413f30  call    cs:__imp_GetCurrentProcess
0x100413f36  mov     rcx, rax; hProcess
0x100413f39  call    cs:__imp_GetPriorityClass
0x100413f3f  mov     ebx, eax
0x100413f41  cmp     eax, 100h
0x100413f46  jnz     loc_100413FD0
0x100413f4c  mov     rcx, cs:__imp_?sm_cpuCount@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_cpuCount
0x100413f53  mov     edx, [rcx]
0x100413f55  cmp     edx, 1
0x100413f58  jnz     short loc_100413FD0
0x100413f5a  call    cs:__imp_GetCurrentProcess
0x100413f60  mov     rcx, rax; hProcess
0x100413f63  lea     edx, [rbx-80h]; dwPriorityClass
0x100413f66  call    cs:__imp_SetPriorityClass
0x100413f6c  test    eax, eax
0x100413f6e  jz      short loc_100413F86
0x100413f70  call    cs:__imp_GetCurrentThread
0x100413f76  mov     rcx, rax; hThread
0x100413f79  mov     edx, r15d; nPriority
0x100413f7c  call    cs:__imp_SetThreadPriority
0x100413f82  test    eax, eax
0x100413f84  jnz     short loc_100413FCB
0x100413f86  call    cs:__imp_GetLastError
0x100413f8c  xor     r9d, r9d
0x100413f8f  lea     rdx, [rbp+2B10h+var_1860]
0x100413f96  mov     ecx, eax
0x100413f98  xor     r8d, r8d
0x100413f9b  call    cs:__imp_?GetOSErrString@@YAPEA_WKAEAVErrorStringHolder@@PEBXK@Z; GetOSErrString(ulong,ErrorStringHolder &,void const *,ulong)
0x100413fa1  lea     rdx, aStartupBoostpr; "StartUp::BoostPriority"
0x100413fa8  mov     ecx, 429Dh; unsigned int
0x100413fad  mov     r8, rax
0x100413fb0  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100413fb5  mov     ecx, 28h ; '('
0x100413fba  mov     r8d, 42Ah
0x100413fc0  mov     edx, 429Dh
0x100413fc5  call    cs:__imp_?SQLExit@@YAXW4SQLEXITCODE@@KK@Z; SQLExit(SQLEXITCODE,ulong,ulong)
0x100413fcb  mov     ebx, 80h
0x100413fd0  xor     esi, esi
0x100413fd2  mov     ecx, esi
0x100413fd4  cmp     ebx, 80h
0x100413fda  setz    cl
0x100413fdd  add     ecx, 430Ah; unsigned int
0x100413fe3  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100413fe8  lea     rcx, [rbp+2B10h+Buffer]; lpBuffer
0x100413fec  mov     [rbp+2B10h+Buffer.dwLength], 40h ; '@'
0x100413ff3  call    cs:__imp_GlobalMemoryStatusEx
0x100413ff9  mov     rdx, [rbp+2B10h+Buffer.ullTotalPhys]
0x100413ffd  mov     ecx, 0C2EFh; unsigned int
0x100414002  shr     rdx, 14h
0x100414006  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x10041400b  mov     rax, cs:__imp_?sm_Priority@SOS_PublicGlobals@@2HA; int SOS_PublicGlobals::sm_Priority
0x100414012  mov     ecx, esi
0x100414014  cmp     ebx, 80h
0x10041401a  cmovz   ecx, r15d
0x10041401e  mov     [rax], ecx
0x100414020  call    cs:__imp_?SetUnhandledExceptionFilter@SOS_OS@@SAXXZ; SOS_OS::SetUnhandledExceptionFilter(void)
0x100414026  call    cs:__imp_?SetInvalidParameterHandler@SOS_OS@@SAP6AXPEB_W00I_K@ZXZ; SOS_OS::SetInvalidParameterHandler(void)
0x10041402c  call    cs:__imp_?SetAbortHandler@SOS_OS@@SAXXZ; SOS_OS::SetAbortHandler(void)
0x100414032  mov     rax, cs:qword_10049F340
0x100414039  test    byte ptr [rax+1C9h], 1
0x100414040  jz      short loc_10041405A
0x100414042  mov     rax, cs:__imp_?SOS_OS_StackBackTraceRoutine@@3P6AGKKPEAPEAXPEAK@ZEA; ushort (*SOS_OS_StackBackTraceRoutine)(ulong,ulong,void * *,ulong *)
0x100414049  mov     rcx, cs:__imp_?DbgEngineStackBackTrace@@YAGKKPEAPEAXPEAK@Z; DbgEngineStackBackTrace(ulong,ulong,void * *,ulong *)
0x100414050  mov     [rax], rcx
0x100414053  mov     rax, cs:qword_10049F340
0x10041405a  mov     rcx, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100414061  mov     rdx, [rcx]
0x100414064  mov     ecx, [rdx+8]
0x100414067  test    ecx, ecx
0x100414069  jz      short loc_100414076
0x10041406b  cmp     ecx, 3
0x10041406e  jz      short loc_100414076
0x100414070  cmp     [rdx+0Ch], r15d
0x100414074  jnz     short loc_100414089
0x100414076  test    byte ptr [rax+1C8h], 40h
0x10041407d  jnz     short loc_100414089
0x10041407f  mov     rax, cs:__imp_?sm_osOptions@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osOptions
0x100414086  and     dword ptr [rax], 0FFFFFFFBh
0x100414089  mov     rax, cs:qword_10049F360
0x100414090  cmp     [rax+38A8h], esi
0x100414096  jz      short loc_1004140A2
0x100414098  mov     rax, cs:__imp_?sm_osOptions@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osOptions
0x10041409f  or      dword ptr [rax], 8
0x1004140a2  mov     rax, cs:__imp_?SOS_OS_CreateTraceBuffRoutine@@3P6APEAVSOS_TraceStreamBuffer@@PEAVIMemObj@@@ZEA; SOS_TraceStreamBuffer * (*SOS_OS_CreateTraceBuffRoutine)(IMemObj *)
0x1004140a9  lea     rcx, GetCerrStreamBuf
0x1004140b0  lea     rbx, [rbp+2B10h+var_860]
0x1004140b7  mov     edi, 40h ; '@'
0x1004140bc  mov     [rax], rcx
0x1004140bf  lea     rcx, ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1004140c6  mov     rax, cs:__imp_?SOS_OS_ErrorLogRoutine@@3P6AXKZZEA; void (*SOS_OS_ErrorLogRoutine)(ulong,...)
0x1004140cd  mov     [rax], rcx
0x1004140d0  lea     rcx, ?SOSLogToErrorLog@@YAXPEB_WZZ; SOSLogToErrorLog(wchar_t const *,...)
0x1004140d7  mov     rax, cs:__imp_?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; void (*SOS_OS_LogUnlocalizedRoutine)(wchar_t const *,...)
0x1004140de  mov     [rax], rcx
0x1004140e1  lea     rcx, ?LogSystemMetadataNotSentToClient@@YAXPEB_WZZ; LogSystemMetadataNotSentToClient(wchar_t const *,...)
0x1004140e8  mov     rax, cs:__imp_?sm_LogSystemMetadataRoutine@SOS_PublicGlobals@@2P6AXPEB_WZZEA; void (*SOS_PublicGlobals::sm_LogSystemMetadataRoutine)(wchar_t const *,...)
0x1004140ef  mov     [rax], rcx
0x1004140f2  lea     rcx, ?SqlDumpExceptionHandler@@YAHPEAU_EXCEPTION_POINTERS@@@Z; SqlDumpExceptionHandler(_EXCEPTION_POINTERS *)
0x1004140f9  mov     rax, cs:__imp_?sm_DumpExceptionHandlerRoutine@SOS_PublicGlobals@@2P6AHPEAU_EXCEPTION_POINTERS@@@ZEA; int (*SOS_PublicGlobals::sm_DumpExceptionHandlerRoutine)(_EXCEPTION_POINTERS *)
0x100414100  mov     [rax], rcx
0x100414103  mov     rax, cs:__imp_?SOS_OS_ExNotificationRoutine@@3P6AXIIIIPEA_WI@ZEA; void (*SOS_OS_ExNotificationRoutine)(uint,uint,uint,uint,wchar_t *,uint)
0x10041410a  mov     rcx, cs:__imp_?ex_sqltrace_event@@YAXIIIIPEA_WI@Z; ex_sqltrace_event(uint,uint,uint,uint,wchar_t *,uint)
0x100414111  mov     [rax], rcx
0x100414114  lea     rcx, ?FGenerateDumpForErrorWrapper@@YAHKH@Z; FGenerateDumpForErrorWrapper(ulong,int)
0x10041411b  mov     rax, cs:__imp_?SOS_OS_ShouldStackDumpForErrorCallBack@@3P6AHKH@ZEA; int (*SOS_OS_ShouldStackDumpForErrorCallBack)(ulong,int)
0x100414122  mov     [rax], rcx
0x100414125  mov     rax, cs:__imp_?SOS_OS_StackTraceRoutine@@3P6AXPEAXPEB_WKPEAPEAX@ZEA; void (*SOS_OS_StackTraceRoutine)(void *,wchar_t const *,ulong,void * *)
0x10041412c  mov     rcx, cs:__imp_?stackTraceCallBack@@YAXPEAXPEB_WKPEAVCDStream@@@Z; stackTraceCallBack(void *,wchar_t const *,ulong,CDStream *)
0x100414133  mov     [rax], rcx
0x100414136  lea     rcx, ?ex_vcallprint_no_dump_no_retval@@YAXHHHPEAD@Z; ex_vcallprint_no_dump_no_retval(int,int,int,char *)
0x10041413d  mov     rax, cs:__imp_?SOS_OS_ExceptionPrintRoutine@@3P6AXHHHPEAD@ZEA; void (*SOS_OS_ExceptionPrintRoutine)(int,int,int,char *)
0x100414144  mov     [rax], rcx
0x100414147  lea     rcx, ?user_log@@YAXHHHKZZ; user_log(int,int,int,ulong,...)
0x10041414e  mov     rax, cs:__imp_?SOS_OS_UserLogRoutine@@3P6AXHHHKZZEA; void (*SOS_OS_UserLogRoutine)(int,int,int,ulong,...)
0x100414155  mov     [rax], rcx
0x100414158  mov     rax, cs:__imp_?SOS_OS_ExPreCallBackRoutine@@3P6AXPEAH000PEAXPEAD@ZEA; void (*SOS_OS_ExPreCallBackRoutine)(int *,int *,int *,int *,void *,char *)
0x10041415f  mov     rcx, cs:__imp_?ex_exception_precallback@@YAXPEAH000PEAXPEAD@Z; ex_exception_precallback(int *,int *,int *,int *,void *,char *)
0x100414166  mov     [rax], rcx
0x100414169  mov     rax, cs:__imp_?SOS_OS_ExPostCallBackRoutine@@3P6AXHHHH@ZEA; void (*SOS_OS_ExPostCallBackRoutine)(int,int,int,int)
0x100414170  mov     rcx, cs:__imp_?ex_exception_postcallback@@YAXHHHH@Z; ex_exception_postcallback(int,int,int,int)
0x100414177  mov     [rax], rcx
0x10041417a  lea     rcx, ?OutOfMemoryHandlerRoutine@SQLFatalHandlers@@SAH_K@Z; SQLFatalHandlers::OutOfMemoryHandlerRoutine(unsigned __int64)
0x100414181  mov     rax, cs:__imp_?sm_OutOfMemoryHandlerRoutine@SOS_PublicGlobals@@2P6AH_K@ZEA; int (*SOS_PublicGlobals::sm_OutOfMemoryHandlerRoutine)(unsigned __int64)
0x100414188  mov     [rax], rcx
0x10041418b  lea     rcx, ?SQLDescribeResourceRoutine@@YAHIPEAEIPEA_WPEAI@Z; SQLDescribeResourceRoutine(uint,uchar *,uint,wchar_t *,uint *)
0x100414192  mov     rax, cs:__imp_?SOS_OS_DescribeResourceRoutine@@3P6AHIPEAEIPEA_WPEAI@ZEA; int (*SOS_OS_DescribeResourceRoutine)(uint,uchar *,uint,wchar_t *,uint *)
0x100414199  mov     [rax], rcx
0x10041419c  mov     rax, cs:__imp_?sm_ExitRoutine@SOS_PublicGlobals@@2P6AXK@ZEA; void (*SOS_PublicGlobals::sm_ExitRoutine)(ulong)
0x1004141a3  mov     rcx, cs:__imp_?SQLExitWrapper@@YAXK@Z; SQLExitWrapper(ulong)
0x1004141aa  mov     [rax], rcx
0x1004141ad  mov     rax, cs:__imp_?SOS_OS_SymbolizeRoutine@@3P6AHPEBQEAXIPEADI@ZEA; int (*SOS_OS_SymbolizeRoutine)(void * const *,uint,char *,uint)
0x1004141b4  mov     rcx, cs:__imp_?SymbolizeFrames@@YAHPEBQEAXIPEADI@Z; SymbolizeFrames(void * const *,uint,char *,uint)
0x1004141bb  mov     [rax], rcx
0x1004141be  lea     rcx, ?CmdLineParamProcessDash_g@@YAXAEAVDkParameter@@@Z; CmdLineParamProcessDash_g(DkParameter &)
0x1004141c5  mov     rax, cs:__imp_?SOS_OS_CriticalExceptionCheckRoutine@@3P6AXI@ZEA; void (*SOS_OS_CriticalExceptionCheckRoutine)(uint)
0x1004141cc  mov     [rax], rcx
0x1004141cf  mov     rax, cs:__imp_?SOS_OS_OverlappedResultRoutine@@3P6AHPEAXPEAU_OVERLAPPED@@PEAKH@ZEA; int (*SOS_OS_OverlappedResultRoutine)(void *,_OVERLAPPED *,ulong *,int)
0x1004141d6  mov     rcx, cs:__imp_?DBGetOverlappedResult@@YAHPEAXPEAU_OVERLAPPED@@PEAKH@Z; DBGetOverlappedResult(void *,_OVERLAPPED *,ulong *,int)
0x1004141dd  mov     [rax], rcx
0x1004141e0  mov     rcx, rbx
0x1004141e3  call    cs:__imp_??0GroupAffinity@@QEAA@XZ; GroupAffinity::GroupAffinity(void)
0x1004141e9  add     rbx, 10h
0x1004141ed  sub     rdi, 1
0x1004141f1  jnz     short loc_1004141E0
0x1004141f3  mov     rax, cs:qword_10049F360
0x1004141fa  movzx   edx, si
0x1004141fd  mov     [rsp+2C10h+var_2BDC], dx
0x100414202  cmp     [rax+38D0h], esi
0x100414208  jnz     short loc_100414238
0x10041420a  cmp     [rax+38D4h], esi
0x100414210  jnz     short loc_100414230
0x100414212  lea     rdx, [rsp+2C10h+var_2BDC]
0x100414217  lea     rcx, [rbp+2B10h+var_860]
0x10041421e  call    cs:__imp_?ReadNodeConfiguration@StartUp@@SAXQEAVGroupAffinity@@PEAF@Z; StartUp::ReadNodeConfiguration(GroupAffinity * const,short *)
0x100414224  movzx   edx, [rsp+2C10h+var_2BDC]
0x100414229  mov     rax, cs:qword_10049F360
0x100414230  cmp     [rax+38D0h], esi
0x100414236  jz      short loc_10041423F
0x100414238  mov     [rsp+2C10h+var_2BDC], si
0x10041423d  jmp     short loc_100414251
0x10041423f  test    dx, dx
0x100414242  jz      short loc_100414251
0x100414244  lea     rcx, [rbp+2B10h+var_860]
0x10041424b  call    cs:__imp_?SetNodeConfiguration@SOS_OS@@SAXPEAVGroupAffinity@@F@Z; SOS_OS::SetNodeConfiguration(GroupAffinity *,short)
0x100414251  call    cs:__imp_?FUseReplicatedServerContext@@YA_NXZ; FUseReplicatedServerContext(void)
0x100414257  test    al, al
0x100414259  mov     rax, cs:qword_10049F360
0x100414260  lea     r12, [rax+3A10h]
0x100414267  jz      short loc_100414270
0x100414269  lea     r12, [rax+6F68h]
0x100414270  mov     rcx, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100414277  mov     r14d, 1
0x10041427d  mov     rdx, [rcx]
0x100414280  mov     ecx, [rdx+8]
0x100414283  test    ecx, ecx
0x100414285  jz      short loc_1004142BD
0x100414287  cmp     ecx, 3
0x10041428a  jz      short loc_1004142BD
0x10041428c  test    byte ptr [rax+0BD7Ch], 20h
0x100414293  jnz     short loc_1004142BD
0x100414295  mov     rcx, cs:qword_10049F340
0x10041429c  movzx   edx, byte ptr [rcx+0C9h]
0x1004142a3  test    dl, 20h
0x1004142a6  jnz     short loc_1004142B7
0x1004142a8  cmp     [r12+309Eh], si
0x1004142b1  jz      short loc_1004142BD
0x1004142b3  test    dl, dl
0x1004142b5  js      short loc_1004142BD
0x1004142b7  mov     [rax+34h], r14d
0x1004142bb  jmp     short loc_1004142C0
0x1004142bd  mov     [rax+34h], esi
0x1004142c0  mov     rax, cs:qword_10049F360
0x1004142c7  cmp     [rax+38A8h], esi
0x1004142cd  jz      short loc_100414310
0x1004142cf  call    cs:__imp_GetXdbServerGlobals
0x1004142d5  cmp     [rax+3FA2h], sil
0x1004142dc  mov     rax, cs:__imp_?sm_osStatus@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStatus
0x1004142e3  jz      short loc_100414340
0x1004142e5  or      dword ptr [rax], 1000h
0x1004142eb  call    cs:__imp_GetXdbServerGlobals
0x1004142f1  cmp     [rax+3FA4h], esi
0x1004142f7  jbe     short loc_100414346
0x1004142f9  call    cs:__imp_GetXdbServerGlobals
0x1004142ff  mov     ecx, [rax+3FA4h]
0x100414305  mov     rax, cs:__imp_?SOS_OS_PhysicalCoresPerSoftNumaThreshold@@3KA; ulong SOS_OS_PhysicalCoresPerSoftNumaThreshold
0x10041430c  mov     [rax], ecx
0x10041430e  jmp     short loc_100414346
0x100414310  cmp     [r12+3547h], sil
0x100414318  jnz     short loc_100414339
0x10041431a  mov     rax, cs:qword_10049F340
0x100414321  test    byte ptr [rax+3F1h], 10h
  ... truncated ...
```

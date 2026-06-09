# BPool::Init(void)

- ea: `0x1016cbca0`
- end: `0x1016cce5a`
- name: `?Init@BPool@@QEAAXXZ`
- size: `4538`
- prototype: `void __fastcall(BPool *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x101ba83c0`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x10045e930`
- `0x1004869c0`
- `0x1004acad0`
- `0x10060e1c0`
- `0x100848a30`
- `0x1016cb890`
- `0x1016cbca0`
- `0x1016cce60`
- `0x1016e1f50`
- `0x1016e22f0`
- `0x1016e8550`
- `0x1016e8a90`
- `0x1016e9ef0`
- `0x1016ec2f0`
- `0x1019213f0`
- `0x101ab19d0`
- `0x1023aea90`
- `0x1023aecb0`
- `0x1023af450`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1016ccd33`
- `KERNEL32!GetProcAddress` at `0x1016ccd81`
- `KERNEL32!GetProcAddress` at `0x1016ccd98`
- `KERNEL32!GetProcAddress` at `0x1016ccd33`
- `KERNEL32!GetProcAddress` at `0x1016ccd81`
- `KERNEL32!GetProcAddress` at `0x1016ccd98`
- `KERNEL32!GetModuleHandleW` at `0x1016ccd20`
- `KERNEL32!GetModuleHandleW` at `0x1016ccd20`
- `KERNEL32!GetSystemInfo` at `0x1016cc326`
- `KERNEL32!GetSystemInfo` at `0x1016cc326`
- `KERNEL32!GlobalMemoryStatusEx` at `0x1016cc14f`
- `KERNEL32!GlobalMemoryStatusEx` at `0x1016cc14f`
- `KERNEL32!InterlockedPushEntrySList` at `0x1016cc7a2`
- `KERNEL32!InterlockedPushEntrySList` at `0x1016cc7e7`
- `KERNEL32!InterlockedPushEntrySList` at `0x1016cc859`
- `KERNEL32!InterlockedPushEntrySList` at `0x1016cc894`
- `KERNEL32!InterlockedPushEntrySList` at `0x1016cc7a2`
- `KERNEL32!InterlockedPushEntrySList` at `0x1016cc7e7`
- `KERNEL32!InterlockedPushEntrySList` at `0x1016cc859`
- `KERNEL32!InterlockedPushEntrySList` at `0x1016cc894`
- `KERNEL32!FindFirstVolumeW` at `0x1016cc1d3`
- `KERNEL32!FindFirstVolumeW` at `0x1016cc1d3`
- `KERNEL32!FindNextVolumeW` at `0x1016cc213`
- `KERNEL32!FindNextVolumeW` at `0x1016cc213`
- `KERNEL32!FindVolumeClose` at `0x1016cc2e3`
- `KERNEL32!FindVolumeClose` at `0x1016cc3e9`
- `KERNEL32!FindVolumeClose` at `0x1016cc2e3`
- `KERNEL32!FindVolumeClose` at `0x1016cc3e9`
- `KERNEL32!QueryPerformanceCounter` at `0x1016cbe58`
- `KERNEL32!QueryPerformanceCounter` at `0x1016cbf22`
- `KERNEL32!QueryPerformanceCounter` at `0x1016cbe58`
- `KERNEL32!QueryPerformanceCounter` at `0x1016cbf22`
- `KERNEL32!GetLastError` at `0x1016cc21d`
- `KERNEL32!GetLastError` at `0x1016cc21d`
- `sqldk!?GetOperatingSystemName@OsInfo@@QEBAQEB_WXZ` at `0x1016cc4ac`
- `sqldk!?GetOperatingSystemName@OsInfo@@QEBAQEB_WXZ` at `0x1016cc4ac`
- `sqldk!?ConfigureMemoryBroker@SOS_MemoryPool@@QEAAXW4MemoryBrokerType@@P6AXPEAVSOS_MemoryBroker@@_JPEAW4NOTIFICATION@3@@Z@Z` at `0x1016cc03c`
- `sqldk!?ConfigureMemoryBroker@SOS_MemoryPool@@QEAAXW4MemoryBrokerType@@P6AXPEAVSOS_MemoryBroker@@_JPEAW4NOTIFICATION@3@@Z@Z` at `0x1016cc03c`
- `sqldk!?ChangeMemoryBrokerPressureType@SOS_MemoryPool@@QEAAXW4MemoryBrokerType@@W4BrokerPressureType@SOS_MemoryBroker@@@Z` at `0x1016cc056`
- `sqldk!?ChangeMemoryBrokerPressureType@SOS_MemoryPool@@QEAAXW4MemoryBrokerType@@W4BrokerPressureType@SOS_MemoryBroker@@@Z` at `0x1016cc056`
- `sqldk!?AllocateLargePageBuffer@MemoryClerkInternal@@QEAAPEAX_K@Z` at `0x1016cca90`
- `sqldk!?AllocateLargePageBuffer@MemoryClerkInternal@@QEAAPEAX_K@Z` at `0x1016cca90`
- `sqldk!?Init@PerCPUDataImpl@@IEAAH_K@Z` at `0x1016ccad2`
- `sqldk!?Init@PerCPUDataImpl@@IEAAH_K@Z` at `0x1016ccde3`
- `sqldk!?Init@PerCPUDataImpl@@IEAAH_K@Z` at `0x1016ccad2`
- `sqldk!?Init@PerCPUDataImpl@@IEAAH_K@Z` at `0x1016ccde3`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1016cc075`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1016cc0cb`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1016cc4ba`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1016cca06`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x1016cc92e`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x1016ccafc`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x1016ccbe5`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x1016cc1b2`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x1016cc494`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x1016cc4a5`
- `sqldk!?SOS_OS_MemoryModel@@3W4SOS_MemoryModel@@A` at `0x1016cc643`
- `sqldk!?sm_IsHotAddMemorySupportEnabled@SOS_PublicGlobals@@2HA` at `0x1016cc35b`
- `sqldk!?sm_osStatus@SOS_PublicGlobals@@2KA` at `0x1016cbd59`
- `sqldk!?MemoryNode_LargePageSize@@3_KA` at `0x1016cc127`
- `sqldk!?MemoryNode_MemoryTargetPages@@3_JA` at `0x1016cc502`
- `sqldk!?SOS_OS_NumberOfMemoryNodeInfos@@3KA` at `0x1016ccc06`
- `sqldk!?SOS_OS_NumberOfMemoryNodeInfos@@3KA` at `0x1016ccc60`
- `sqldk!?SOS_OS_NumberOfMemoryNodeInfos@@3KA` at `0x1016ccc8e`
- `sqldk!?SOS_OS_NumberOfMemoryNodeInfos@@3KA` at `0x1016ccccf`
- `sqldk!?sm_SysInfo@SOS_PublicGlobals@@2U_SYSTEM_INFO@@A` at `0x1016cca70`
- `sqldk!?sm_CommonCriteriaModeEnabled@SOS_PublicGlobals@@2HA` at `0x1016cbdb6`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016cbe47`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016cbe88`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016cbef9`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016cbf37`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x1016cbe94`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x1016cbf4d`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x1016cc1b9`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x1016cc49b`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x1016cc1b9`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x1016cc49b`
- `sqldk!?VirtualAlloc@MemoryClerkInternal@@QEAAPEAXPEAX_KKK@Z` at `0x1016cc67e`
- `sqldk!?VirtualAlloc@MemoryClerkInternal@@QEAAPEAXPEAX_KKK@Z` at `0x1016cc67e`
- `sqldk!?GetCommittedPotentialPages@MemoryNode@@SA_JXZ` at `0x1016cc8a8`
- `sqldk!?GetCommittedPotentialPages@MemoryNode@@SA_JXZ` at `0x1016cc8a8`
- `sqldk!?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z` at `0x1016cc029`
- `sqldk!?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z` at `0x1016cc044`
- `sqldk!?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z` at `0x1016cc029`
- `sqldk!?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z` at `0x1016cc044`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x1016cc69f`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x1016ccaad`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x1016ccaf2`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x1016ccc58`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x1016cc69f`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x1016ccaad`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x1016ccaf2`
- `sqldk!?SQLExit@@YAXW4SQLEXITCODE@@@Z` at `0x1016ccc58`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016cc276`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016cc2c1`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016cc276`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x1016cc2c1`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016cbce9`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016cbcff`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016cbce9`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016cbcff`
- `sqldk!SystemThread_TlsIndex` at `0x1016cc246`
- `sqldk!SystemThread_TlsIndex` at `0x1016cc292`
- `sqldk!SystemThread_TlsIndex` at `0x1016cc729`
- `sqldk!SystemThread_TlsIndex` at `0x1016cc7f6`
- `sqldk!SystemThread_TlsIndex` at `0x1016ccb2b`
- `sqldk!SystemThread_TlsIndex` at `0x1016ccb8c`
- `sqldk!SystemThread_TlsOffset` at `0x1016cc24f`
- `sqldk!SystemThread_TlsOffset` at `0x1016cc29b`
- `sqldk!SystemThread_TlsOffset` at `0x1016cc732`
- `sqldk!SystemThread_TlsOffset` at `0x1016cc7ff`
- `sqldk!SystemThread_TlsOffset` at `0x1016ccb34`
- `sqldk!SystemThread_TlsOffset` at `0x1016ccb95`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016cc74e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016cc81b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016ccb4d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016ccbae`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016cc74e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016cc81b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016ccb4d`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016ccbae`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x1016cbcf6`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x1016cbcf6`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x1016cc902`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x1016cc924`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x1016cc902`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x1016cc924`

## string_xrefs

- `0x1016cc916`: `EnableResilientBufferPoolExtension`
- `0x1016cc8fb`: `SQL.Config`
- `0x1016cc91d`: `SQL.Config`
- `0x1016ccd19`: `kernel32.dll`
- `0x1016ccc42`: `BPool NUMA access stats array`

## pseudocode

```c

```

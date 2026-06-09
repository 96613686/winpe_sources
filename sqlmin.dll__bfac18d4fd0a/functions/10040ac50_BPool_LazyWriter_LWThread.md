# BPool::LazyWriter(LWThread *)

- ea: `0x10040ac50`
- end: `0x10040b3ea`
- name: `?LazyWriter@BPool@@AEAAXPEAVLWThread@@@Z`
- size: `1946`
- prototype: `void __fastcall(BPool *__hidden this, struct LWThread *)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1016c8b40`

## callees

- `0x100401010`
- `0x100402a60`
- `0x10040abd0`
- `0x10040ac50`
- `0x10040b3f0`
- `0x10040bc20`
- `0x10040bd60`
- `0x10040cde0`
- `0x1004162a0`
- `0x100418690`
- `0x100424500`
- `0x1004732e0`
- `0x10047b3f0`
- `0x1004acad0`
- `0x1004c37b0`
- `0x1004c39d0`
- `0x1005486c0`
- `0x10056c3c0`
- `0x1005c8fe0`
- `0x1005cda20`
- `0x1005d8b90`
- `0x10060e1c0`
- `0x1006446e0`
- `0x100644890`
- `0x100644a40`
- `0x100644bf0`
- `0x100644da0`
- `0x1006c5e70`
- `0x1006c6280`
- `0x1006c6560`
- `0x10072cac0`
- `0x100848a30`
- `0x1016d9cb0`
- `0x1016d9e00`
- `0x1016e5170`
- `0x1023aea90`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x1016db54e`
- `KERNEL32!VirtualFree` at `0x1016db54e`
- `KERNEL32!VirtualProtect` at `0x1016db2f3`
- `KERNEL32!VirtualProtect` at `0x1016db2f3`
- `KERNEL32!QueryPerformanceCounter` at `0x10040acac`
- `KERNEL32!QueryPerformanceCounter` at `0x10040acec`
- `KERNEL32!QueryPerformanceCounter` at `0x10040b103`
- `KERNEL32!QueryPerformanceCounter` at `0x10040b25d`
- `KERNEL32!QueryPerformanceCounter` at `0x1016da395`
- `KERNEL32!QueryPerformanceCounter` at `0x1016da4f8`
- `KERNEL32!QueryPerformanceCounter` at `0x1016db0eb`
- `KERNEL32!QueryPerformanceCounter` at `0x1016db138`
- `KERNEL32!QueryPerformanceCounter` at `0x1016db426`
- `KERNEL32!QueryPerformanceCounter` at `0x1016db46e`
- `KERNEL32!QueryPerformanceCounter` at `0x10040acac`
- `KERNEL32!QueryPerformanceCounter` at `0x10040acec`
- `KERNEL32!QueryPerformanceCounter` at `0x10040b103`
- `KERNEL32!QueryPerformanceCounter` at `0x10040b25d`
- `KERNEL32!QueryPerformanceCounter` at `0x1016da395`
- `KERNEL32!QueryPerformanceCounter` at `0x1016da4f8`
- `KERNEL32!QueryPerformanceCounter` at `0x1016db0eb`
- `KERNEL32!QueryPerformanceCounter` at `0x1016db138`
- `KERNEL32!QueryPerformanceCounter` at `0x1016db426`
- `KERNEL32!QueryPerformanceCounter` at `0x1016db46e`
- `sqldk!?TransferMemory@SOS_MemoryPool@@QEAAX_JW4MemoryBrokerType@@1@Z` at `0x1016da600`
- `sqldk!?TransferMemory@SOS_MemoryPool@@QEAAX_JW4MemoryBrokerType@@1@Z` at `0x1016db644`
- `sqldk!?TransferMemory@SOS_MemoryPool@@QEAAX_JW4MemoryBrokerType@@1@Z` at `0x1016da600`
- `sqldk!?TransferMemory@SOS_MemoryPool@@QEAAX_JW4MemoryBrokerType@@1@Z` at `0x1016db644`
- `sqldk!?TurnOff@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1016db5f9`
- `sqldk!?TurnOff@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1016db5f9`
- `sqldk!?SetNotificationInterface@MemoryClerkInternal@@QEAAXPEAVNotificationInterface@1@@Z` at `0x10040ad9e`
- `sqldk!?SetNotificationInterface@MemoryClerkInternal@@QEAAXPEAVNotificationInterface@1@@Z` at `0x10040ad9e`
- `sqldk!?IsNotificationInterfaceSet@MemoryClerkInternal@@QEBAHXZ` at `0x10040ad86`
- `sqldk!?IsNotificationInterfaceSet@MemoryClerkInternal@@QEBAHXZ` at `0x10040ad86`
- `sqldk!?AddMemoryBrokerClerk@ResourceMonitor@@QEAAXPEAVMemoryBrokerClerk@@@Z` at `0x10040adcd`
- `sqldk!?AddMemoryBrokerClerk@ResourceMonitor@@QEAAXPEAVMemoryBrokerClerk@@@Z` at `0x10040adcd`
- `sqldk!?AddExternalCache@ResourceMonitor@@QEAAXPEAVExternalCache@@@Z` at `0x10040ade1`
- `sqldk!?AddExternalCache@ResourceMonitor@@QEAAXPEAVExternalCache@@@Z` at `0x10040ade1`
- `sqldk!?CheckForIOCompletion@SOS_Scheduler@@SAXW4IOType@1@W4IOCheck@IOQueue@@@Z` at `0x1016da3cc`
- `sqldk!?CheckForIOCompletion@SOS_Scheduler@@SAXW4IOType@1@W4IOCheck@IOQueue@@@Z` at `0x1016da3cc`
- `sqldk!?RecalculateTarget@MemoryNode@@SAXXZ` at `0x10040c804`
- `sqldk!?RecalculateTarget@MemoryNode@@SAXXZ` at `0x10040c804`
- `sqldk!?LatestBenefitSlope@IntegralController@@QEBANXZ` at `0x10040c8f7`
- `sqldk!?LatestBenefitSlope@IntegralController@@QEBANXZ` at `0x10040c8f7`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1004aca2f`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1016db382`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1016db4ea`
- `sqldk!?MemoryNode_MaxMemoryPagesLimit@@3_JA` at `0x1004aca91`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1016db089`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1016db3c8`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x1016db537`
- `sqldk!?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A` at `0x10040ada4`
- `sqldk!?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A` at `0x10040ae87`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1016db0f8`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1016db433`
- `sqldk!?MemoryNode_MemoryTargetPages@@3_JA` at `0x10040b1fa`
- `sqldk!?MemoryNode_MinMemoryPagesLimit@@3_JA` at `0x1004aca73`
- `sqldk!?MemoryNode_MinMemoryPagesLimit@@3_JA` at `0x1016db56b`
- `sqldk!?SOS_OS_NumberOfMemoryNodeInfos@@3KA` at `0x10040ae9d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040ac98`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040acc3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040b0ef`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040b249`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040b274`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016da1ef`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016da385`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016da4e9`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016da529`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016db0d7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016db124`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016db416`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1016db45e`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x10040b284`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x1016da1b2`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x1016da1fb`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x1016da534`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c80a`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c83a`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c882`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c8a5`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c919`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c94e`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040c9b8`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040ca32`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040ca67`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040cb97`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040cbf3`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040cc6c`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040cca4`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040ccdc`
- `sqldk!?m_PerfCountersEnabled@CommonGlobalState@@2_NA` at `0x10040cd25`
- `sqldk!?VirtualAlloc@MemoryClerkInternal@@QEAAPEAXPEAX_KKK@Z` at `0x1016da748`
- `sqldk!?VirtualAlloc@MemoryClerkInternal@@QEAAPEAXPEAX_KKK@Z` at `0x1016da748`
- `sqldk!?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z` at `0x1016da5ed`
- `sqldk!?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z` at `0x1016db631`
- `sqldk!?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z` at `0x1016da5ed`
- `sqldk!?GetPool@MemoryPoolManager@@SAPEAVSOS_MemoryPool@@K@Z` at `0x1016db631`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1016db5dc`
- `sqldk!?TurnOn@CGlobalTraceFlags@@SA_NGW4FlagUsage@1@@Z` at `0x1016db5dc`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x1016db22c`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x1016db22c`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10040b18d`
- `sqldk!?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z` at `0x10040b18d`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016da710`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016da727`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016da710`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1016da727`
- `sqldk!SystemThread_TlsIndex` at `0x10040ae2b`
- `sqldk!SystemThread_TlsIndex` at `0x10040aec0`
- `sqldk!SystemThread_TlsIndex` at `0x10040af19`
- `sqldk!SystemThread_TlsIndex` at `0x10040af58`
- `sqldk!SystemThread_TlsIndex` at `0x10040b32f`
- `sqldk!SystemThread_TlsIndex` at `0x10040b38d`
- `sqldk!SystemThread_TlsIndex` at `0x10040b4aa`
- `sqldk!SystemThread_TlsIndex` at `0x1016da3db`
- `sqldk!SystemThread_TlsIndex` at `0x1016daf75`
- `sqldk!SystemThread_TlsIndex` at `0x1016db0a9`
- `sqldk!SystemThread_TlsIndex` at `0x1016db18f`
- `sqldk!SystemThread_TlsIndex` at `0x1016db3e8`
- `sqldk!SystemThread_TlsOffset` at `0x10040ae34`
- `sqldk!SystemThread_TlsOffset` at `0x10040aec9`
- `sqldk!SystemThread_TlsOffset` at `0x10040af22`
- `sqldk!SystemThread_TlsOffset` at `0x10040af61`
- `sqldk!SystemThread_TlsOffset` at `0x10040b338`
- `sqldk!SystemThread_TlsOffset` at `0x10040b396`
- `sqldk!SystemThread_TlsOffset` at `0x10040b4b3`
- `sqldk!SystemThread_TlsOffset` at `0x1016da3e4`
- `sqldk!SystemThread_TlsOffset` at `0x1016daf7e`
- `sqldk!SystemThread_TlsOffset` at `0x1016db0b2`
- `sqldk!SystemThread_TlsOffset` at `0x1016db198`
- `sqldk!SystemThread_TlsOffset` at `0x1016db3f1`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040ae4f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da241`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da269`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da3ff`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da5c4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da61f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016daf97`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db608`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10040ae4f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da241`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da269`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da3ff`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da5c4`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016da61f`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016daf97`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1016db608`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x1016da71e`
- `sqldk!?GetDefaultMemoryClerksForNode@PerProcessGlobals@@QEAAPEAPEAVMemoryClerk@@G@Z` at `0x1016da71e`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040b3d7`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016da254`
- `sqldk!??_V@YAXPEAX@Z` at `0x10040b3d7`
- `sqldk!??_V@YAXPEAX@Z` at `0x1016da254`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1016db38e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1016db4f6`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1016db38e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1016db4f6`

## string_xrefs

- `0x1016dafcf`: `Bad Page Processing task`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
// Hidden C++ exception states: #wind=5
void __fastcall __noreturn BPool::LazyWriter(BPool *this, unsigned __int64 a2)
{
  struct LWThread *v2; // rsi
  BPool *v3; // r13
  LARGE_INTEGER v4; // r8
  LARGE_INTEGER v5; // rcx
  int v6; // r12d
  unsigned int v7; // r15d
  DirtyPageMgr *QuadPart; // rdi
  __int64 v9; // rbx
  unsigned int v10; // ecx
  __int64 v11; // rbx
  __int64 v12; // rax
  int v13; // r8d
  __int64 v14; // r9
  __int64 v15; // rsi
  __int64 v16; // rbx
  void *v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // rax
  char v20; // cl
  __int64 v21; // rdx
  unsigned __int64 v22; // r14
  char *v23; // r15
  signed __int64 v24; // rbx
  RecoveryUnit **v25; // rsi
  signed __int64 v26; // rcx
  unsigned int j; // edi
  int v28; // esi
  __int64 v29; // rdx
  struct LWThread *v30; // rsi
  int v31; // ebx
  __int64 v32; // r8
  int v33; // ecx
  LARGE_INTEGER v34; // rcx
  unsigned __int64 v35; // r14
  unsigned int v36; // edx
  __int64 v37; // rbx
  __int64 v38; // r13
  _QWORD *v39; // r13
  unsigned int v40; // r15d
  __int64 *v41; // rsi
  __int64 v42; // r14
  __int64 v43; // rsi
  __int64 v44; // rbx
  void *v45; // rcx
  __int64 v46; // rbx
  __int64 v47; // r13
  _QWORD *v48; // r13
  unsigned int v49; // r15d
  __int64 *v50; // rsi
  __int64 v51; // r14
  __int64 v52; // rsi
  unsigned __int16 v53; // bx
  int v54; // r8d
  char *v55; // rdx
  __int64 v56; // r9
  int v57; // r8d
  char *v58; // rdx
  double v59; // xmm0_8
  unsigned __int64 v60; // rax
  char *v61; // rdx
  __int64 v62; // r9
  int v63; // r8d
  char *v64; // rdx
  unsigned int v65; // esi
  signed __int64 v66; // r9
  int v67; // edx
  __int64 v68; // rcx
  __int64 **v69; // rcx
  __int64 *v70; // rcx
  __int64 v71; // rdx
  __int64 v72; // rtt
  signed __int64 v73; // r9
  int v74; // edx
  __int64 v75; // rcx
  __int64 *v76; // rcx
  __int64 v77; // rcx
  signed __int64 v78; // rdx
  __int64 v79; // rdx
  signed __int64 v80; // r10
  signed __int64 v81; // r11
  unsigned int v82; // eax
  __int64 v83; // rcx
  _DWORD *v84; // r8
  __int64 v85; // r9
  __int64 v86; // rcx
  __int64 *v87; // rcx
  __int64 v88; // rcx
  signed __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 *v91; // rcx
  __int64 v92; // rcx
  signed __int64 v93; // rdx
  unsigned __int64 v94; // r8
  __int64 v95; // r9
  __int16 v96; // dx
  char *v97; // rdx
  char *v98; // rdx
  char *v99; // rdx
  unsigned __int64 v100; // rcx
  char *v101; // rdx
  BPool *v102; // rcx
  __int64 v103; // rax
  __int64 v104; // r8
  unsigned int v105; // edx
  unsigned __int64 v106; // rcx
  unsigned __int64 v107; // rax
  signed __int64 v108; // rbx
  RecoveryUnit **v109; // r10
  signed __int64 v110; // rcx
  unsigned int i; // r8d
  __int64 v112; // rbx
  _QWORD *v113; // r8
  unsigned __int64 v114; // rax
  unsigned __int64 v115; // rdx
  __int64 v116; // rcx
  __int64 v117; // rax
  bool v118; // zf
  char v119; // al
  DirtyPageMgr *v120; // rcx
  unsigned __int64 v121; // rcx
  unsigned __int64 v122; // rdx
  int v123; // eax
  struct SOS_MemoryPool *v124; // rax
  int v125; // eax
  PerProcessGlobals *ClientProcessGlobals; // rax
  struct MemoryClerk **DefaultMemoryClerksForNode; // rbx
  __int64 v128; // rtt
  unsigned __int64 v129; // r8
  volatile signed __int64 **v130; // rdx
  unsigned __int64 v131; // r8
  char *v132; // rdx
  unsigned __int64 v133; // r10
  char *v134; // rdx
  unsigned __int64 v135; // r11
  char *v136; // rdx
  _DWORD *v137; // rax
  _QWORD *v138; // rcx
  __int64 v139; // r10
  char *v140; // r8
  __int64 v141; // rbx
  __int64 v142; // rcx
  __int64 *v143; // rsi
  DirtyPageMgr *v144; // rbx
  signed __int64 UniqueThread_low; // r15
  __int64 v146; // r14
  __int64 v147; // r8
  DirtyPageMgr *v148; // rcx
  signed __int64 v149; // rax
  _QWORD *v150; // rcx
  __int64 v151; // rax
  __int64 v152; // r8
  __int64 v153; // rax
  ISOSHost_TaskImpl *v154; // rcx
  unsigned int v155; // edx
  SOS_Node *v156; // rcx
  __int64 v157; // rbx
  __int64 *v158; // r15
  __int64 v159; // rsi
  DirtyPageMgr *v160; // rbx
  signed __int64 v161; // r12
  __int64 *v162; // rcx
  unsigned __int64 v163; // r8
  SOS_ObjectStore *v164; // rcx
  unsigned int PoolIdForObject; // eax
  __int64 v166; // r10
  _QWORD *v167; // r8
  __int64 v168; // rax
  __int64 v169; // rcx
  int v170; // r8d
  __int64 v171; // r14
  __int64 v172; // r8
  __int64 v173; // rcx
  DirtyPageMgr *v174; // rcx
  signed __int64 v175; // rax
  int v176; // r8d
  char v177; // cl
  char v178; // al
  struct SOS_MemoryPool *Pool; // rax
  signed __int32 v180[6]; // [rsp+8h] [rbp-100h] BYREF
  void (*v181)(struct SOS_IOCompRequest *); // [rsp+28h] [rbp-E0h]
  unsigned __int64 v182; // [rsp+58h] [rbp-B0h]
  unsigned __int64 v183; // [rsp+60h] [rbp-A8h]
  unsigned __int64 v184; // [rsp+68h] [rbp-A0h]
  volatile signed __int64 *v185; // [rsp+70h] [rbp-98h] BYREF
  __int64 v186; // [rsp+78h] [rbp-90h]
  struct LWThread *v187; // [rsp+80h] [rbp-88h]
  DWORD flOldProtect; // [rsp+88h] [rbp-80h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+90h] [rbp-78h] BYREF
  LARGE_INTEGER v190; // [rsp+98h] [rbp-70h] BYREF
  LARGE_INTEGER v191; // [rsp+A0h] [rbp-68h] BYREF
  struct SOS_ResourceGroup *GroupForBackgroundWrites; // [rsp+A8h] [rbp-60h] BYREF
  char *v193; // [rsp+B0h] [rbp-58h]
  LARGE_INTEGER v194; // [rsp+B8h] [rbp-50h] BYREF
  LARGE_INTEGER v195; // [rsp+C0h] [rbp-48h] BYREF
  LARGE_INTEGER v196; // [rsp+C8h] [rbp-40h] BYREF
  LARGE_INTEGER v197; // [rsp+D0h] [rbp-38h] BYREF
  LARGE_INTEGER v198; // [rsp+D8h] [rbp-30h] BYREF
  LARGE_INTEGER v199; // [rsp+E0h] [rbp-28h] BYREF
  LARGE_INTEGER v200; // [rsp+E8h] [rbp-20h] BYREF
  int v201; // [rsp+F0h] [rbp-18h] BYREF
  __int64 v202; // [rsp+F8h] [rbp-10h]
  __int64 v203; // [rsp+100h] [rbp-8h]
  __int64 v204; // [rsp+108h] [rbp+0h]
  __int64 v205; // [rsp+110h] [rbp+8h]
  __int64 v206; // [rsp+118h] [rbp+10h]
  char *v207; // [rsp+128h] [rbp+20h] BYREF
  int v208; // [rsp+130h] [rbp+28h]
  int v209; // [rsp+160h] [rbp+58h]
  int v210; // [rsp+164h] [rbp+5Ch]
  char v211[8]; // [rsp+168h] [rbp+60h] BYREF
  int v212; // [rsp+170h] [rbp+68h]
  int v213; // [rsp+178h] [rbp+70h]
  _QWORD *v214; // [rsp+180h] [rbp+78h]
  char *v215; // [rsp+188h] [rbp+80h]
  __int64 v216; // [rsp+190h] [rbp+88h]
  _QWORD v217[2]; // [rsp+198h] [rbp+90h] BYREF
  char v218; // [rsp+1A8h] [rbp+A0h] BYREF
  __int64 v219; // [rsp+3B8h] [rbp+2B0h]
  __int64 v220; // [rsp+3C0h] [rbp+2B8h]
  signed __int64 v221; // [rsp+3C8h] [rbp+2C0h] BYREF
  unsigned int v222; // [rsp+3D0h] [rbp+2C8h]
  char v223[8]; // [rsp+3D8h] [rbp+2D0h] BYREF
  int v224; // [rsp+3E0h] [rbp+2D8h]
  int v225; // [rsp+3E8h] [rbp+2E0h]
  _QWORD *v226; // [rsp+3F0h] [rbp+2E8h]
  char *v227; // [rsp+3F8h] [rbp+2F0h]
  __int64 v228; // [rsp+400h] [rbp+2F8h]
  _QWORD v229[2]; // [rsp+408h] [rbp+300h] BYREF
  char v230; // [rsp+418h] [rbp+310h] BYREF
  __int64 v231; // [rsp+628h] [rbp+520h]
  __int64 v232; // [rsp+630h] [rbp+528h]
  signed __int64 v233; // [rsp+638h] [rbp+530h] BYREF
  unsigned int v234; // [rsp+640h] [rbp+538h]
  char v235[8]; // [rsp+648h] [rbp+540h] BYREF
  int v236; // [rsp+650h] [rbp+548h]
  int v237; // [rsp+658h] [rbp+550h]
  _QWORD *v238; // [rsp+660h] [rbp+558h]
  char *v239; // [rsp+668h] [rbp+560h]
  __int64 v240; // [rsp+670h] [rbp+568h]
  _QWORD v241[2]; // [rsp+678h] [rbp+570h] BYREF
  char v242; // [rsp+688h] [rbp+580h] BYREF
  __int64 v243; // [rsp+898h] [rbp+790h]
  __int64 v244; // [rsp+8A0h] [rbp+798h]
  __int64 v245; // [rsp+8A8h] [rbp+7A0h] BYREF
  char v246[8]; // [rsp+8B8h] [rbp+7B0h] BYREF
  int v247; // [rsp+8C0h] [rbp+7B8h]
  int v248; // [rsp+8C8h] [rbp+7C0h]
  _QWORD *v249; // [rsp+8D0h] [rbp+7C8h]
  char *v250; // [rsp+8D8h] [rbp+7D0h]
  __int64 v251; // [rsp+8E0h] [rbp+7D8h]
  _QWORD v252[2]; // [rsp+8E8h] [rbp+7E0h] BYREF
  char v253; // [rsp+8F8h] [rbp+7F0h] BYREF
  __int64 v254; // [rsp+B08h] [rbp+A00h]
  __int64 v255; // [rsp+B10h] [rbp+A08h]
  __int64 v256; // [rsp+B18h] [rbp+A10h] BYREF
  char v257[8]; // [rsp+B28h] [rbp+A20h] BYREF
  int v258; // [rsp+B30h] [rbp+A28h]
  int v259; // [rsp+B38h] [rbp+A30h]
  _QWORD *v260; // [rsp+B40h] [rbp+A38h]
  char *v261; // [rsp+B48h] [rbp+A40h]
  __int64 v262; // [rsp+B50h] [rbp+A48h]
  _QWORD v263[2]; // [rsp+B58h] [rbp+A50h] BYREF
  char v264; // [rsp+B68h] [rbp+A60h] BYREF
  __int64 v265; // [rsp+D78h] [rbp+C70h]
  __int64 v266; // [rsp+D80h] [rbp+C78h]
  __int64 v267; // [rsp+D88h] [rbp+C80h] BYREF
  struct LWThread *v269; // [rsp+E40h] [rbp+D38h]
  int v270; // [rsp+E48h] [rbp+D40h]
  int v271; // [rsp+E50h] [rbp+D48h]

  v269 = (struct LWThread *)a2;
  v206 = -2;
  v2 = (struct LWThread *)a2;
  v3 = this;
  if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    QueryPerformanceCounter(&PerformanceCount);
    v4 = PerformanceCount;
  }
  else
  {
    v4.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
  }
  if ( v4.QuadPart == -1 )
  {
    LODWORD(v184) = -1;
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
LABEL_5:
      QueryPerformanceCounter(&v190);
      v5 = v190;
      goto LABEL_6;
    }
  }
  else
  {
    if ( Base_PublicGlobals::sm_invariantTscAvailable )
    {
      v184 = (unsigned __int64)(1000 * v4.QuadPart) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
      goto LABEL_5;
    }
    a2 = v4.QuadPart / 0x2710uLL;
    LODWORD(v184) = v4.QuadPart / 0x2710uLL;
  }
  v5.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
LABEL_6:
  if ( v5.QuadPart == -1 )
  {
    v183 = -1;
  }
  else if ( Base_PublicGlobals::sm_invariantTscAvailable )
  {
    v4 = Base_PublicGlobals::sm_QueryPerformanceFrequency;
    a2 = (unsigned __int64)(1000 * v5.QuadPart) % Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
    v183 = (unsigned __int64)(1000 * v5.QuadPart) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
  }
  else
  {
    a2 = v5.QuadPart / 0x2710uLL;
    v183 = v5.QuadPart / 0x2710uLL;
  }
  v6 = 0;
  v271 = 0;
  v7 = -1;
  v270 = -1;
  QuadPart = 0;
  v201 = 4194488;
  v202 = 0;
  v204 = 0;
  v203 = 0;
  v205 = 0;
  v207 = (char *)qword_10317B628 + 4736;
  v208 = 0;
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))DescriptorAllocator<BUF,16>::Iterator::Reset)(
    &v207,
    a2,
    (LARGE_INTEGER)v4.QuadPart,
    0x346DC5D63886594BLL);
  v209 = 0;
  v210 = 1;
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)v3 + 167, (signed __int64)v2, 0) )
  {
    if ( !MemoryClerkInternal::IsNotificationInterfaceSet(*((MemoryClerkInternal **)v3 + 163)) )
      MemoryClerkInternal::SetNotificationInterface(*((MemoryClerkInternal **)v3 + 163), (BPool *)((char *)v3 + 1344));
    v9 = SOS_PublicGlobals::sm_NodeManager[5];
    if ( v9 && (*(_BYTE *)(v9 + 1568) & 0x10) != 0 )
      v9 = 0;
    ResourceMonitor::AddMemoryBrokerClerk((ResourceMonitor *)(v9 + 944), (BPool *)((char *)v3 + 1376));
    ResourceMonitor::AddExternalCache((ResourceMonitor *)(v9 + 944), (BPool *)((char *)v3 + 1352));
  }
  v187 = (struct LWThread *)*((_QWORD *)v3 + 167);
  *((_DWORD *)v2 + 18) = 1;
  v10 = 0;
  while ( v2 != (BPool *)((char *)v3 + 1024 * (unsigned __int64)v10 + 40600) )
  {
    if ( ++v10 >= 0x40 )
      goto LABEL_18;
  }
  v7 = v10;
  v270 = v10;
LABEL_18:
  v11 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v12 = *(_QWORD *)(v11 + 256);
  if ( !v12 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v12 = *(_QWORD *)(v11 + 256);
  }
  if ( (*(_BYTE *)(*(_QWORD *)(v12 + 608) + 5104LL) & 2) != 0 )
  {
    v13 = 8;
    if ( LODWORD(SOS_PublicGlobals::sm_NodeManager[4]) < 8 )
      v13 = SOS_PublicGlobals::sm_NodeManager[4];
    v14 = SOS_PublicGlobals::sm_NodeManager[4];
    if ( v14 <= SOS_OS_NumberOfMemoryNodeInfos )
      LODWORD(v14) = SOS_OS_NumberOfMemoryNodeInfos;
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                                      + SystemThread_TlsOffset
                                      + 8LL)
                          + 96LL)
              + 1248LL) = ((unsigned __int64)v2 - *((_QWORD *)v3 + 5040)) / 0x50 + v13 + v14;
  }
  while ( 1 )
  {
    v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v16 = *(_QWORD *)(v15 + 256);
    if ( !v16 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v16 = *(_QWORD *)(v15 + 256);
    }
    v17 = *(void **)(v16 + 496);
    if ( v17 )
    {
      operator delete[](v17);
      *(_QWORD *)(v16 + 496) = 0;
    }
    v18 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v19 = *(_QWORD *)(v18 + 256);
    if ( !v19 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v19 = *(_QWORD *)(v18 + 256);
    }
    v20 = *((_BYTE *)v3 + 108);
    v21 = *((_QWORD *)v3 + 12);
    v22 = v21 + ((unsigned __int64)*(unsigned int *)(v19 + 76) << v20);
    v182 = v22;
    if ( !*(_BYTE *)(v22 + 25) )
    {
      v22 = *((_QWORD *)v3 + 14);
      v182 = v22;
    }
    if ( v7 != -1 && *(unsigned __int8 *)(v22 + 24) != v7 )
    {
      v107 = (unsigned __int64)v7 << 10;
      if ( *(_DWORD *)((char *)v3 + v107 + 40456) )
      {
        v22 = v21 + ((unsigned __int64)*(unsigned __int16 *)((char *)v3 + v107 + 40466) << v20);
        v182 = v22;
      }
    }
    v23 = (char *)v3 + 1024 * (unsigned __int64)*(unsigned __int8 *)(v22 + 24) + 40448;
    v193 = v23;
    if ( *((_QWORD *)v269 + 7) )
    {
      _m_prefetchw((char *)v269 + 56);
      do
        v108 = *((_QWORD *)v269 + 7);
      while ( v108 != _InterlockedCompareExchange64((volatile signed __int64 *)v269 + 7, 0, v108) );
      if ( v108 )
      {
        do
        {
          v109 = (RecoveryUnit **)v108;
          v110 = v108;
          v108 = *(_QWORD *)(v108 + 8);
          for ( i = 1; v108; ++i )
          {
            if ( i >= 0x40 )
              break;
            if ( *(_QWORD *)(v108 + 144) != *(_QWORD *)(v110 + 144) )
              break;
            if ( *(_DWORD *)(v108 + 112) != *(_DWORD *)(v110 + 112) + 1 )
              break;
            if ( *(_WORD *)(v108 + 116) != *(_WORD *)(v110 + 116) )
              break;
            v110 = v108;
            v108 = *(_QWORD *)(v108 + 8);
          }
          *(_QWORD *)(v110 + 8) = 0;
          RecoveryUnit::ScatterRead(
            v109[18],
            (struct BUF *)v109,
            i,
            (const struct PageId *)(v109 + 14),
            (void (*)(struct SOS_IOCompRequest *))BPool::ReadPageCompletion,
            v109,
            0,
            0,
            0);
        }
        while ( v108 );
        v6 = v271;
      }
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v191);
        QuadPart = (DirtyPageMgr *)v191.QuadPart;
      }
      else
      {
        QuadPart = MEMORY[0x7FFE0008];
      }
    }
    if ( *((_QWORD *)v269 + 8) )
    {
      _m_prefetchw((char *)v269 + 64);
      do
        v24 = *((_QWORD *)v269 + 8);
      while ( v24 != _InterlockedCompareExchange64((volatile signed __int64 *)v269 + 8, 0, v24) );
      if ( v24 )
      {
        do
        {
          v25 = (RecoveryUnit **)v24;
          v26 = v24;
          v24 = *(_QWORD *)(v24 + 8);
          for ( j = 1; v24; ++j )
          {
            if ( j >= 0x40 )
              break;
            if ( *(_QWORD *)(v24 + 144) != *(_QWORD *)(v26 + 144) )
              break;
            if ( *(_DWORD *)(v24 + 112) != *(_DWORD *)(v26 + 112) + 1 )
              break;
            if ( *(_WORD *)(v24 + 116) != *(_WORD *)(v26 + 116) )
              break;
            v26 = v24;
            v24 = *(_QWORD *)(v24 + 8);
          }
          *(_QWORD *)(v26 + 8) = 0;
          GroupForBackgroundWrites = (struct SOS_ResourceGroup *)BPool::GetGroupForBackgroundWrites(
                                                                   v3,
                                                                   *((_QWORD *)v25[18] + 214),
                                                                   j,
                                                                   1);
          RecoveryUnit::GatherWrite(
            v25[18],
            (struct BUF *)v25,
            j,
            (const struct PageId *)(v25 + 14),
            (void (*)(struct SOS_IOCompRequest *))BPool::WritePageCompletion,
            v25,
            GroupForBackgroundWrites,
            0,
            0);
          SOS_AutoReleaseResourceGroup::UnhookAndRelease((SOS_AutoReleaseResourceGroup *)&GroupForBackgroundWrites);
        }
        while ( v24 );
        v22 = v182;
        v23 = v193;
        v6 = v271;
      }
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v194);
        QuadPart = (DirtyPageMgr *)v194.QuadPart;
      }
      else
      {
        QuadPart = MEMORY[0x7FFE0008];
      }
    }
    if ( (unsigned int)BPool::ShouldAdvanceClock(v3, (const struct BufferPartition *)v22)
      && (unsigned int)BPool::ShouldShrink(v3, (const struct NumaNode *)v23) )
    {
      v28 = 1;
LABEL_238:
      SOS_Scheduler::CheckForIOCompletion(0, 1);
      v112 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
      v113 = *(_QWORD **)(v112 + 256);
      if ( !v113 )
      {
        SystemThread::MakeMiniSOSThread(0);
        v113 = *(_QWORD **)(v112 + 256);
      }
      v114 = __rdtsc();
      v115 = v113[104];
      if ( v114 <= v115 && (v115 == 0x7FFFFFFFFFFFFFFFLL || v115 - v114 <= *(_QWORD *)(v113[76] + 3568LL)) )
      {
        v116 = v113[75];
        if ( (*(_DWORD *)(v116 + 188) & 4) != 0 )
        {
          v117 = *(_QWORD *)(v116 + 152);
          if ( (*(_BYTE *)(v117 + 616) & 1) == 0 && (*(_DWORD *)(v117 + 800) & 0x180) == 0 )
          {
            v31 = 2;
            goto LABEL_247;
          }
        }
        v123 = 0;
      }
      else
      {
        v123 = SOS_Task::Sleep(0, yieldWait);
      }
      v31 = v123;
LABEL_247:
      v118 = v28 == 0;
      v30 = v269;
      if ( v118 )
        goto LABEL_59;
LABEL_248:
      if ( v31 || (*((_BYTE *)v3 + 4360) & 1) == 0 && !*((_DWORD *)v23 + 3) || (v119 = v23[16], v23[16] = 1, v119) )
      {
        BPool::ReplenishFreeList(v3, (struct BufferPartition *const)v22, 0, 0, 0);
      }
      else
      {
        BPool::ReplenishFreeList(v3, (struct BufferPartition *const)v22, 0, 0, 1);
        v23[16] = 0;
      }
      goto LABEL_59;
    }
    v28 = 0;
    if ( *((_QWORD *)v3 + 128 * (unsigned __int64)*(unsigned __int8 *)(v22 + 24) + 5088) > *((_QWORD *)v3
                                                                                           + 128
                                                                                           * (unsigned __int64)*(unsigned __int8 *)(v22 + 24)
                                                                                           + 5086) >> 2 )
      goto LABEL_238;
    if ( (*((_BYTE *)v3 + 36) & 1) != 0 )
    {
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v195);
        v120 = (DirtyPageMgr *)v195.QuadPart;
      }
      else
      {
        v120 = MEMORY[0x7FFE0008];
      }
      if ( v120 < QuadPart )
      {
        v121 = 0;
      }
      else
      {
        v121 = v120 - QuadPart;
        if ( v121 == -1 )
          goto LABEL_55;
      }
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
        v122 = 1000 * v121 / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
      else
        v122 = v121 / 0x2710;
      if ( v122 <= 0xA )
        goto LABEL_238;
    }
LABEL_55:
    v29 = 0xFFFFFFFFLL;
    v30 = v269;
    if ( v187 == v269 )
      v29 = 1000;
    LOBYTE(v181) = 1;
    v31 = WaitableBase::Wait((char *)v269 + 8, v29, &v201, 0, (_DWORD)v181);
    if ( (unsigned int)BPool::ShouldAdvanceClock(v3, (const struct BufferPartition *)v22)
      && (unsigned int)BPool::ShouldShrink(v3, (const struct NumaNode *)v23) )
    {
      goto LABEL_248;
    }
LABEL_59:
    if ( *((_QWORD *)v3 + 128 * (unsigned __int64)*(unsigned __int8 *)(v22 + 24) + 5088) > *((_QWORD *)v3
                                                                                           + 128
                                                                                           * (unsigned __int64)*(unsigned __int8 *)(v22 + 24)
                                                                                           + 5086) >> 2 )
      BPool::ShrinkSimulatedBufs(v3, (struct BufferPartition *const)v22);
    if ( v187 == v30 )
    {
      v32 = 1;
      if ( *((_DWORD *)v3 + 22) > 1u )
        v32 = *((unsigned int *)v3 + 22);
      v33 = 20;
      if ( (int)((double)(int)(MemoryNode_MemoryTargetPages / 300 / v32) * 0.05) > 20 )
        v33 = (int)((double)(int)(MemoryNode_MemoryTargetPages / 300 / v32) * 0.05);
      if ( *((_DWORD *)v3 + 8) != v33 )
        *((_DWORD *)v3 + 8) = v33;
      if ( Base_PublicGlobals::sm_invariantTscAvailable )
      {
        QueryPerformanceCounter(&v196);
        v34 = v196;
      }
      else
      {
        v34.QuadPart = (LONGLONG)MEMORY[0x7FFE0008];
      }
      if ( v34.QuadPart == -1 )
      {
        v35 = -1;
      }
      else
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          v35 = (unsigned __int64)(1000 * v34.QuadPart) / Base_PublicGlobals::sm_QueryPerformanceFrequency.QuadPart;
          v182 = v35;
          goto LABEL_73;
        }
        v35 = v34.QuadPart / 0x2710uLL;
      }
      v182 = v35;
LABEL_73:
      if ( ((((unsigned __int8)byte_10317ABE9 >> 2) ^ (unsigned __int8)(*((_DWORD *)v3 + 9) >> 2)) & 1) != 0 )
        *((_DWORD *)v3 + 9) ^= ((unsigned __int8)*((_DWORD *)v3 + 9)
                              ^ (unsigned __int8)~(unsigned __int8)*((_DWORD *)v3 + 9))
                             & 4;
      v36 = *((_DWORD *)v3 + 11);
      if ( ((((unsigned __int8)byte_10317ABE4 >> 4) ^ (unsigned __int8)(v36 >> 1)) & 1) == 0 )
      {
        v125 = v36 ^ ((unsigned __int8)v36 ^ (unsigned __int8)~(_BYTE)v36) & 2;
        LOBYTE(v36) = v36 ^ (v36 ^ ~(_BYTE)v36) & 2;
        *((_DWORD *)v3 + 11) = v125;
      }
      if ( (v36 & 0x20) != 0
        && !byte_10316E664
        && (byte_10317ABE5 & 2) == 0
        && !*((_BYTE *)GetServerConfiguration() + 13646) )
      {
        *((_DWORD *)v3 + 11) ^= ((unsigned __int8)*((_DWORD *)v3 + 11)
                               ^ (unsigned __int8)~(unsigned __int8)*((_DWORD *)v3 + 11))
                              & 0x20
                              ^ (*((_BYTE *)v3 + 44)
                               ^ ((unsigned __int8)*((_DWORD *)v3 + 11)
                                ^ (unsigned __int8)~(unsigned __int8)*((_DWORD *)v3 + 11))
                               & 0x20
                               ^ (unsigned __int8)~(*((_BYTE *)v3 + 44)
                                                  ^ (*((_DWORD *)v3 + 11)
                                                   ^ ~(unsigned __int8)*((_DWORD *)v3 + 11))
                                                  & 0x20))
                              & 0x40;
      }
      if ( (unsigned int)(v35 - v6) < 0x3E8 )
      {
LABEL_79:
        if ( (unsigned int)(v35 - v183) >= 0x2710 )
        {
          LODWORD(v183) = v35;
          v104 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 504LL))(s_pServerConf);
          v105 = *(_DWORD *)(v104 + 20);
          if ( v105 < 0x10 )
            v105 = 16;
          MemoryNode_MinMemoryPagesLimit = (unsigned __int64)v105 << 7;
          v106 = 128;
          if ( (unsigned __int64)*(unsigned int *)(v104 + 32) << 7 >= 0x80 )
            v106 = (unsigned __int64)*(unsigned int *)(v104 + 32) << 7;
          MemoryNode_MaxMemoryPagesLimit = v106;
          if ( dword_103172528 )
          {
            if ( !byte_10316E665
              || (!byte_10316EA31 || word_103185B6E ? (v177 = 0) : (v177 = 1),
                  !byte_10316EA32 || !word_103185B6E ? (v178 = 0) : (v178 = 1),
                  (v177 || v178) && dword_103184474 && !FPDWFeaturesExposed()) )
            {
              CGlobalTraceFlags::TurnOff(8063, 0);
            }
            else
            {
              CGlobalTraceFlags::TurnOn(8063, 0);
            }
          }
          BPool::ConfigurePartitions(v3, 0, 0x40u);
        }
        if ( (unsigned int)(v35 - v184) >= 0xEA60 )
        {
          LODWORD(v184) = v35;
          BUF::UpdateCycleBasedThreshold();
        }
        v37 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v38 = *(_QWORD *)(v37 + 256);
        if ( !v38 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v38 = *(_QWORD *)(v37 + 256);
        }
        v39 = *(_QWORD **)(v38 + 600);
        v40 = 0;
        v41 = v39 + 57;
        do
        {
          v42 = *v41;
          if ( *v41 )
          {
            Pool = MemoryPoolManager::GetPool(v40);
            SOS_MemoryPool::TransferMemory(Pool, v42 / 0x2000, 6);
            v39[54] -= v42;
            *v41 -= v42;
            v39[56] -= v42;
          }
          ++v40;
          ++v41;
        }
        while ( v40 < 0x40 );
        goto LABEL_88;
      }
      if ( (byte_10316E762 || (byte_10317ABE6 & 4) != 0) && (qword_10317ABEC & 0x400) == 0 )
      {
        if ( !*((_QWORD *)v3 + 525) )
        {
          ClientProcessGlobals = (PerProcessGlobals *)SOS_OS::GetClientProcessGlobals();
          DefaultMemoryClerksForNode = PerProcessGlobals::GetDefaultMemoryClerksForNode(ClientProcessGlobals, 0);
          SOS_OS::GetClientProcessGlobals();
          *((_QWORD *)v3 + 525) = MemoryClerkInternal::VirtualAlloc(
                                    DefaultMemoryClerksForNode[4],
                                    0,
                                    *((_QWORD *)v3 + 528),
                                    0x1000u,
                                    4u);
          _InterlockedOr(v180, 0);
        }
        if ( !*((_DWORD *)v3 + 1052) && *((_QWORD *)v3 + 525) )
          *((_DWORD *)v3 + 1052) = 1;
      }
      else if ( *((_DWORD *)v3 + 1052) )
      {
        *((_DWORD *)v3 + 1052) = 0;
      }
      MemoryNode::RecalculateTarget();
      if ( CommonGlobalState::m_PerfCountersEnabled )
      {
        v52 = 0;
        v53 = 0;
        do
          v52 += BPool::HashedCount(v3, v53++);
        while ( (unsigned int)v53 <= *((_DWORD *)v3 + 192) );
        v54 = 0;
        if ( CommonGlobalState::m_PerfCountersEnabled )
        {
          v55 = 0;
          if ( pCounterLookupBlocks )
            v55 = (char *)pCounterLookupBlocks + 2048;
          if ( v55 && *(_QWORD *)v55 )
          {
            *(_QWORD *)(*(_QWORD *)v55 + 48LL) = v52;
            v54 = 1;
          }
        }
        if ( (g_XeSqlMinPkg_enabledBitmap & 4) != 0 && v54 )
        {
          v236 = 0x10000;
          v237 = 0;
          v238 = v241;
          v239 = &v242;
          v243 = 0;
          v240 = 0;
          v244 = 0;
          v241[0] = &v245;
          v241[1] = 8;
          v245 = v52;
          XeSqlPkg::buffer_manager_database_pages::Publish((XeSqlPkg::buffer_manager_database_pages *)v235);
        }
      }
      if ( CommonGlobalState::m_PerfCountersEnabled )
      {
        v56 = BPool::GetLWSpeed(v3) / 0x3E8;
        v57 = 0;
        v58 = 0;
        if ( pCounterLookupBlocks )
          v58 = (char *)pCounterLookupBlocks + 2048;
        if ( v58 && *(_QWORD *)v58 )
        {
          *(_QWORD *)(*(_QWORD *)v58 + 128LL) = v56;
          v57 = 1;
        }
        if ( (g_XeSqlMinPkg_enabledBitmap & 8) != 0 && v57 )
        {
          v247 = 0x10000;
          v248 = 0;
          v249 = v252;
          v250 = &v253;
          v254 = 0;
          v251 = 0;
          v255 = 0;
          v252[0] = &v256;
          v252[1] = 8;
          v256 = v56;
          XeSqlPkg::buffer_manager_page_life_expectancy::Publish((XeSqlPkg::buffer_manager_page_life_expectancy *)v246);
        }
      }
      v59 = COERCE_DOUBLE(COERCE_UNSIGNED_INT64(IntegralController::LatestBenefitSlope((BPool *)((char *)v3 + 1456))) ^ _xmm)
          * 1.0e10;
      v60 = 0;
      if ( v59 >= 9.223372036854776e18 )
      {
        v59 = v59 - 9.223372036854776e18;
        if ( v59 < 9.223372036854776e18 )
          v60 = 0x8000000000000000uLL;
      }
      if ( CommonGlobalState::m_PerfCountersEnabled )
      {
        v61 = 0;
        if ( pCounterLookupBlocks )
          v61 = (char *)pCounterLookupBlocks + 2048;
        if ( v61 && *(_QWORD *)v61 )
          *(_QWORD *)(*(_QWORD *)v61 + 64LL) = v60 + (unsigned int)(int)v59;
      }
      if ( CommonGlobalState::m_PerfCountersEnabled )
      {
        v62 = *((_QWORD *)v3 + 544);
        v63 = 0;
        v64 = 0;
        if ( pCounterLookupBlocks )
          v64 = (char *)pCounterLookupBlocks + 2048;
        if ( v64 && *(_QWORD *)v64 )
        {
          *(_QWORD *)(*(_QWORD *)v64 + 56LL) = v62;
          v63 = 1;
        }
        if ( (g_XeSqlMinPkg_enabledBitmap & 0x10) != 0 && v63 )
        {
          v258 = 0x10000;
          v259 = 0;
          v260 = v263;
          v261 = &v264;
          v265 = 0;
          v262 = 0;
          v266 = 0;
          v263[0] = &v267;
          v263[1] = 8;
          v267 = v62;
          XeSqlPkg::buffer_manager_target_pages::Publish((XeSqlPkg::buffer_manager_target_pages *)v257);
        }
      }
      v65 = 0;
      do
      {
        if ( *((_DWORD *)v3 + v65 + 127) )
        {
          if ( CommonGlobalState::m_PerfCountersEnabled )
          {
            v66 = *((_QWORD *)v3 + 128 * (unsigned __int64)v65 + 5086);
            v67 = 0;
            if ( v65 < 0x10000 )
            {
              v68 = (__int64)*(&pCounterLookupBlocks + ((unsigned __int64)v65 >> 8));
              if ( v68 )
              {
                v69 = (__int64 **)(v68 + 8LL * (unsigned __int8)v65 + 4096);
                if ( v69 )
                {
                  v70 = *v69;
                  if ( v70 )
                  {
                    v71 = *v70;
                    v72 = *v70;
                    if ( v72 != _InterlockedCompareExchange64(v70, v66, *v70) )
                    {
                      _m_prefetchw(v70);
                      do
                      {
                        _mm_pause();
                        v71 = *v70;
                        v128 = *v70;
                      }
                      while ( v128 != _InterlockedCompareExchange64(v70, v66, *v70) );
                    }
                    if ( (g_fObjectHasTotalInstance & 4) != 0 )
                    {
                      v129 = v66 - v71;
                      v130 = 0;
                      if ( pCounterLookupBlocks )
                        v130 = (volatile signed __int64 **)((char *)pCounterLookupBlocks + 4096);
                      if ( v130 && *v130 )
                        _InterlockedExchangeAdd64(*v130, v129);
                    }
                    v67 = 1;
                  }
                }
              }
            }
            if ( (g_XeSqlMinPkg_enabledBitmap & 0x20) != 0 && v67 )
            {
              v212 = 0x10000;
              v213 = 0;
              v214 = v217;
              v215 = &v218;
              v219 = 0;
              v216 = 0;
              v220 = 0;
              v217[0] = &v221;
              v217[1] = 12;
              v221 = v66;
              v222 = v65;
              XeSqlPkg::buffer_node_database_pages::Publish((XeSqlPkg::buffer_node_database_pages *)v211);
            }
          }
          if ( CommonGlobalState::m_PerfCountersEnabled )
          {
            v73 = NumaNode::CycleTime((BPool *)((char *)v3 + 1024 * (unsigned __int64)v65 + 40448)) / 0x3E8;
            v74 = 0;
            if ( v65 < 0x10000 )
            {
              v75 = (__int64)*(&pCounterLookupBlocks + ((unsigned __int64)v65 >> 8));
              if ( v75 )
              {
                v76 = (__int64 *)(v75 + 8LL * (unsigned __int8)v65 + 4096);
                if ( v76 )
                {
                  v77 = *v76;
                  if ( v77 )
                  {
                    v78 = *(_QWORD *)(v77 + 8);
                    if ( v78 != _InterlockedCompareExchange64((volatile signed __int64 *)(v77 + 8), v73, v78) )
                    {
                      _m_prefetchw((const void *)(v77 + 8));
                      do
                      {
                        _mm_pause();
                        v78 = *(_QWORD *)(v77 + 8);
                      }
                      while ( v78 != _InterlockedCompareExchange64((volatile signed __int64 *)(v77 + 8), v73, v78) );
                    }
                    if ( (g_fObjectHasTotalInstance & 4) != 0 )
                    {
                      v131 = v73 - v78;
                      v132 = 0;
                      if ( pCounterLookupBlocks )
                        v132 = (char *)pCounterLookupBlocks + 4096;
                      if ( v132 && *(_QWORD *)v132 )
                        _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v132 + 8LL), v131);
                    }
                    v74 = 1;
                  }
                }
              }
            }
            if ( (g_XeSqlMinPkg_enabledBitmap & 0x40) != 0 && v74 )
            {
              v224 = 0x10000;
              v225 = 0;
              v226 = v229;
              v227 = &v230;
              v231 = 0;
              v228 = 0;
              v232 = 0;
              v229[0] = &v233;
              v229[1] = 12;
              v233 = v73;
              v234 = v65;
              XeSqlPkg::buffer_node_page_life_expectancy::Publish((XeSqlPkg::buffer_node_page_life_expectancy *)v223);
            }
          }
          v79 = *((_QWORD *)v3 + 128 * (unsigned __int64)v65 + 5111);
          v80 = *(_QWORD *)(96LL * v65 + v79)
              + *(_QWORD *)(96LL * v65 + v79 + 32)
              + *(_QWORD *)(96LL * v65 + v79 + 48)
              + *(_QWORD *)(96LL * v65 + v79 + 64)
              + *(_QWORD *)(96LL * v65 + v79 + 80)
              + *(_QWORD *)(96LL * v65 + v79 + 8)
              + *(_QWORD *)(96LL * v65 + v79 + 16)
              + *(_QWORD *)(96LL * v65 + v79 + 24)
              + *(_QWORD *)(v79 + 96LL * v65 + 40)
              + *(_QWORD *)(96LL * v65 + v79 + 56)
              + *(_QWORD *)(96LL * v65 + v79 + 72)
              + *(_QWORD *)(96LL * v65 + v79 + 88);
          v81 = -v80;
          v82 = *((_DWORD *)v3 + 192);
          if ( v82 )
          {
            v83 = 0;
            v84 = (_DWORD *)((char *)v3 + 508);
            v85 = v82;
            do
            {
              if ( *v84 )
                v81 += *(_QWORD *)(v83 + v79 + 80)
                     + *(_QWORD *)(v83 + v79)
                     + *(_QWORD *)(v83 + v79 + 64)
                     + *(_QWORD *)(v83 + v79 + 48)
                     + *(_QWORD *)(v83 + v79 + 32)
                     + *(_QWORD *)(v83 + v79 + 8)
                     + *(_QWORD *)(v83 + v79 + 16)
                     + *(_QWORD *)(v83 + v79 + 24)
                     + *(_QWORD *)(v83 + v79 + 40)
                     + *(_QWORD *)(v83 + v79 + 56)
                     + *(_QWORD *)(v83 + v79 + 72)
                     + *(_QWORD *)(v83 + v79 + 88);
              ++v84;
              v83 += 96;
              --v85;
            }
            while ( v85 );
          }
          if ( CommonGlobalState::m_PerfCountersEnabled && v65 < 0x10000 )
          {
            v86 = (__int64)*(&pCounterLookupBlocks + ((unsigned __int64)v65 >> 8));
            if ( v86 )
            {
              v87 = (__int64 *)(v86 + 8LL * (unsigned __int8)v65 + 4096);
              if ( v87 )
              {
                v88 = *v87;
                if ( v88 )
                {
                  v89 = *(_QWORD *)(v88 + 16);
                  if ( v89 != _InterlockedCompareExchange64((volatile signed __int64 *)(v88 + 16), v80, v89) )
                  {
                    _m_prefetchw((const void *)(v88 + 16));
                    do
                    {
                      _mm_pause();
                      v89 = *(_QWORD *)(v88 + 16);
                    }
                    while ( v89 != _InterlockedCompareExchange64((volatile signed __int64 *)(v88 + 16), v80, v89) );
                  }
                  if ( (g_fObjectHasTotalInstance & 4) != 0 )
                  {
                    v133 = v80 - v89;
                    v134 = 0;
                    if ( pCounterLookupBlocks )
                      v134 = (char *)pCounterLookupBlocks + 4096;
                    if ( v134 && *(_QWORD *)v134 )
                      _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v134 + 16LL), v133);
                  }
                }
              }
            }
          }
          if ( CommonGlobalState::m_PerfCountersEnabled && v65 < 0x10000 )
          {
            v90 = (__int64)*(&pCounterLookupBlocks + ((unsigned __int64)v65 >> 8));
            if ( v90 )
            {
              v91 = (__int64 *)(v90 + 8LL * (unsigned __int8)v65 + 4096);
              if ( v91 )
              {
                v92 = *v91;
                if ( v92 )
                {
                  v93 = *(_QWORD *)(v92 + 24);
                  if ( v93 != _InterlockedCompareExchange64((volatile signed __int64 *)(v92 + 24), v81, v93) )
                  {
                    _m_prefetchw((const void *)(v92 + 24));
                    do
                    {
                      _mm_pause();
                      v93 = *(_QWORD *)(v92 + 24);
                    }
                    while ( v93 != _InterlockedCompareExchange64((volatile signed __int64 *)(v92 + 24), v81, v93) );
                  }
                  if ( (g_fObjectHasTotalInstance & 4) != 0 )
                  {
                    v135 = v81 - v93;
                    v136 = 0;
                    if ( pCounterLookupBlocks )
                      v136 = (char *)pCounterLookupBlocks + 4096;
                    if ( v136 && *(_QWORD *)v136 )
                      _InterlockedExchangeAdd64((volatile signed __int64 *)(*(_QWORD *)v136 + 24LL), v135);
                  }
                }
              }
            }
          }
        }
        v94 = 0;
        v95 = 0;
        v96 = 0;
        if ( (unsigned int)(*((_DWORD *)v3 + 26496) - 5) <= 1 )
        {
          v137 = (_DWORD *)((char *)v3 + 252);
          v138 = (_QWORD *)((char *)v3 + 41344);
          v139 = 2;
          do
          {
            if ( *(v137 - 1) )
            {
              v94 += v138[8];
              v95 += *v138;
              ++v96;
            }
            if ( *v137 )
            {
              v94 += v138[136];
              v95 += v138[128];
              ++v96;
            }
            if ( v137[1] )
            {
              v94 += v138[264];
              v95 += v138[256];
              ++v96;
            }
            if ( v137[2] )
            {
              v94 += v138[392];
              v95 += v138[384];
              ++v96;
            }
            if ( v137[3] )
            {
              v94 += v138[520];
              v95 += v138[512];
              ++v96;
            }
            if ( v137[4] )
            {
              v94 += v138[648];
              v95 += v138[640];
              ++v96;
            }
            if ( v137[5] )
            {
              v94 += v138[776];
              v95 += v138[768];
              ++v96;
            }
            if ( v137[6] )
            {
              v94 += v138[904];
              v95 += v138[896];
              ++v96;
            }
            if ( v137[7] )
            {
              v94 += v138[1032];
              v95 += v138[1024];
              ++v96;
            }
            if ( v137[8] )
            {
              v94 += v138[1160];
              v95 += v138[1152];
              ++v96;
            }
            if ( v137[9] )
            {
              v94 += v138[1288];
              v95 += v138[1280];
              ++v96;
            }
            if ( v137[10] )
            {
              v94 += v138[1416];
              v95 += v138[1408];
              ++v96;
            }
            if ( v137[11] )
            {
              v94 += v138[1544];
              v95 += v138[1536];
              ++v96;
            }
            if ( v137[12] )
            {
              v94 += v138[1672];
              v95 += v138[1664];
              ++v96;
            }
            if ( v137[13] )
            {
              v94 += v138[1800];
              v95 += v138[1792];
              ++v96;
            }
            if ( v137[14] )
            {
              v94 += v138[1928];
              v95 += v138[1920];
              ++v96;
            }
            if ( v137[15] )
            {
              v94 += v138[2056];
              v95 += v138[2048];
              ++v96;
            }
            if ( v137[16] )
            {
              v94 += v138[2184];
              v95 += v138[2176];
              ++v96;
            }
            if ( v137[17] )
            {
              v94 += v138[2312];
              v95 += v138[2304];
              ++v96;
            }
            if ( v137[18] )
            {
              v94 += v138[2440];
              v95 += v138[2432];
              ++v96;
            }
            if ( v137[19] )
            {
              v94 += v138[2568];
              v95 += v138[2560];
              ++v96;
            }
            if ( v137[20] )
            {
              v94 += v138[2696];
              v95 += v138[2688];
              ++v96;
            }
            if ( v137[21] )
            {
              v94 += v138[2824];
              v95 += v138[2816];
              ++v96;
            }
            if ( v137[22] )
            {
              v94 += v138[2952];
              v95 += v138[2944];
              ++v96;
            }
            if ( v137[23] )
            {
              v94 += v138[3080];
              v95 += v138[3072];
              ++v96;
            }
            if ( v137[24] )
            {
              v94 += v138[3208];
              v95 += v138[3200];
              ++v96;
            }
            if ( v137[25] )
            {
              v94 += v138[3336];
              v95 += v138[3328];
              ++v96;
            }
            if ( v137[26] )
            {
              v94 += v138[3464];
              v95 += v138[3456];
              ++v96;
            }
            if ( v137[27] )
            {
              v94 += v138[3592];
              v95 += v138[3584];
              ++v96;
            }
            if ( v137[28] )
            {
              v94 += v138[3720];
              v95 += v138[3712];
              ++v96;
            }
            if ( v137[29] )
            {
              v94 += v138[3848];
              v95 += v138[3840];
              ++v96;
            }
            if ( v137[30] )
            {
              v94 += v138[3976];
              v95 += v138[3968];
              ++v96;
            }
            v137 += 32;
            v138 += 4096;
            --v139;
          }
          while ( v139 );
          if ( v96 )
            v94 /= (unsigned __int64)v96;
          else
            v94 = 0;
        }
        if ( CommonGlobalState::m_PerfCountersEnabled )
        {
          v97 = 0;
          if ( pCounterLookupBlocks )
            v97 = (char *)pCounterLookupBlocks + 2048;
          if ( v97 && *(_QWORD *)v97 )
            *(_QWORD *)(*(_QWORD *)v97 + 192LL) = v94;
        }
        if ( CommonGlobalState::m_PerfCountersEnabled )
        {
          v98 = 0;
          if ( pCounterLookupBlocks )
            v98 = (char *)pCounterLookupBlocks + 2048;
          if ( v98 && *(_QWORD *)v98 )
            *(_QWORD *)(*(_QWORD *)v98 + 168LL) = v95;
        }
        if ( CommonGlobalState::m_PerfCountersEnabled )
        {
          v99 = 0;
          if ( pCounterLookupBlocks )
            v99 = (char *)pCounterLookupBlocks + 2048;
          if ( v99 && *(_QWORD *)v99 )
            *(_QWORD *)(*(_QWORD *)v99 + 176LL) = *((_QWORD *)v3 + 520) - v95;
        }
        v100 = *((_QWORD *)v3 + 520);
        if ( v100 )
        {
          if ( CommonGlobalState::m_PerfCountersEnabled )
          {
            v140 = 0;
            if ( pCounterLookupBlocks )
              v140 = (char *)pCounterLookupBlocks + 2048;
            if ( v140 && *(_QWORD *)v140 )
              *(_QWORD *)(*(_QWORD *)v140 + 184LL) = 100 * v95 / v100;
          }
        }
        else if ( CommonGlobalState::m_PerfCountersEnabled )
        {
          v101 = 0;
          if ( pCounterLookupBlocks )
            v101 = (char *)pCounterLookupBlocks + 2048;
          if ( v101 && *(_QWORD *)v101 )
            *(_QWORD *)(*(_QWORD *)v101 + 184LL) = 0;
        }
        ++v65;
      }
      while ( v65 <= *((_DWORD *)v3 + 192) );
      LODWORD(v35) = v182;
      SQLMemoryReport::UpdatePerfCounters();
      *((_WORD *)v3 + 388) = (unsigned int)v35 / 0x3E8;
      if ( (*((_BYTE *)v3 + 44) & 4) != 0
        && (dword_10316ECB0 & 0x20) == 0
        && !_InterlockedCompareExchange((volatile signed __int32 *)v3 + 10, 1, 0) )
      {
        BPool::SniffConstantPages(v102, (struct BufIter *)&v207);
        _InterlockedExchange((volatile __int32 *)v3 + 10, 0);
      }
      if ( *((_QWORD *)v3 + 447) < *((_QWORD *)v3 + 446) && !*((_QWORD *)v3 + 448) )
      {
        v141 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        v142 = *(_QWORD *)(v141 + 256);
        if ( !v142 )
        {
          SystemThread::MakeMiniSOSThread(0);
          v142 = *(_QWORD *)(v141 + 256);
        }
        if ( (unsigned int)SOS_Node::EnqueueTaskDirect(
                             *(_QWORD *)(v142 + 992),
                             BPool::BadPageMemoryNotification,
                             0,
                             0,
                             (char *)v3 + 3584,
                             0) )
          scierrlog(0x42E0u, L"Bad Page Processing task");
        goto LABEL_204;
      }
      v103 = *((_QWORD *)v3 + 448);
      if ( v103 && *(_DWORD *)(v103 + 184) == 2 )
      {
        v143 = (__int64 *)*((_QWORD *)v3 + 448);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v143 + 10, 0xFFFFFFFF) != 1 )
          goto LABEL_413;
        if ( v143[3] )
        {
          TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v143 + 2);
          goto LABEL_413;
        }
        if ( *((_DWORD *)v143 + 46) == 2 )
        {
          v185 = (volatile signed __int64 *)(v143[20] + 4952);
          LODWORD(v186) = 0;
          v144 = 0;
          UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
          if ( *(_DWORD *)v185 || _InterlockedCompareExchange64(v185, UniqueThread_low, 0) )
          {
            v146 = 0;
            if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
            {
              v147 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                   + SystemThread_TlsOffset;
              if ( v147 && *(_QWORD *)(v147 + 272) == v147 )
                v146 = *(_QWORD *)(v147 + 256);
              if ( v146 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v197);
                  v144 = (DirtyPageMgr *)v197.QuadPart;
                }
                else
                {
                  v144 = MEMORY[0x7FFE0008];
                }
              }
            }
            if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
              Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v185, UniqueThread_low);
            else
              Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v185, v146, UniqueThread_low);
            if ( v146 )
            {
              if ( Base_PublicGlobals::sm_invariantTscAvailable )
              {
                QueryPerformanceCounter(&v198);
                v148 = (DirtyPageMgr *)v198.QuadPart;
              }
              else
              {
                v148 = MEMORY[0x7FFE0008];
              }
              v149 = 0;
              if ( v148 >= v144 )
                v149 = v148 - v144;
              *(_QWORD *)(v146 + 3192) += v149;
            }
          }
          LODWORD(v186) = 1;
          v150 = (_QWORD *)v143[1];
          v151 = *v143;
          *(_QWORD *)(v151 + 8) = v150;
          *v150 = v151;
          v143[1] = 0;
          *v143 = 0;
          SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(&v185);
        }
        v152 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v152
          && *(_QWORD *)(v152 + 272) == v152
          && (v153 = *(_QWORD *)(v152 + 256)) != 0
          && *(__int64 **)(v153 + 528) == v143 )
        {
          v154 = (ISOSHost_TaskImpl *)(v143 - 1);
          if ( !v143 )
            v154 = 0;
          v155 = 0;
LABEL_440:
          ISOSHost_TaskImpl::`scalar deleting destructor'(v154, v155);
        }
        else
        {
          v156 = (SOS_Node *)v143[21];
          if ( v156 && *((_QWORD *)v156 + 30) && !SOS_Node::IsTaskStoreDisabled(v156) )
          {
            v157 = *(_QWORD *)(v143[21] + 240);
            v158 = v143 - 1;
            ISOSHost_TaskImpl::`scalar deleting destructor'((ISOSHost_TaskImpl *)(v143 - 1), 0);
            v159 = *(_QWORD *)(v157 + 2016);
            v160 = 0;
            v161 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
            if ( *(_DWORD *)(v159 + 40)
              || _InterlockedCompareExchange64((volatile signed __int64 *)(v159 + 40), v161, 0) )
            {
              v171 = 0;
              if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
              {
                v172 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex)
                     + SystemThread_TlsOffset;
                if ( v172 && *(_QWORD *)(v172 + 272) == v172 )
                  v171 = *(_QWORD *)(v172 + 256);
                if ( v171 )
                {
                  if ( Base_PublicGlobals::sm_invariantTscAvailable )
                  {
                    QueryPerformanceCounter(&v199);
                    v160 = (DirtyPageMgr *)v199.QuadPart;
                  }
                  else
                  {
                    v160 = MEMORY[0x7FFE0008];
                  }
                }
              }
              v173 = v159 + 40;
              if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
                Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v173, v161);
              else
                Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v173, v171, v161);
              if ( v171 )
              {
                if ( Base_PublicGlobals::sm_invariantTscAvailable )
                {
                  QueryPerformanceCounter(&v200);
                  v174 = (DirtyPageMgr *)v200.QuadPart;
                }
                else
                {
                  v174 = MEMORY[0x7FFE0008];
                }
                v175 = 0;
                if ( v174 >= v160 )
                  v175 = v174 - v160;
                *(_QWORD *)(v171 + 3192) += v175;
              }
            }
            if ( *(_QWORD *)(v159 + 8) >= *(_QWORD *)v159 )
            {
              if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v176 = rand();
                if ( v176 == 5 * (v176 / 5) )
                  Spinlock<34,1,268435714>::UpdateStatSnapshot();
              }
              *(_QWORD *)(v159 + 40) = 0;
              (*(void (__fastcall **)(__int64 *))(v159 + 48))(v158);
              v3 = this;
            }
            else
            {
              if ( *(_BYTE *)(*(_QWORD *)(v159 + 32) + 5820LL) )
              {
                v162 = (__int64 *)(v159 + 16 * ((*(_DWORD *)(v159 + 1176) & 0x3F) + 9LL));
                *v158 = *v162;
                if ( !*v162 )
                  v162[1] = (__int64)v158;
                *v162 = (__int64)v158;
                ++*(_QWORD *)(v159 + 1176);
                VirtualProtect(v158, 0x1000u, 1u, &flOldProtect);
              }
              else
              {
                *v158 = *(_QWORD *)(v159 + 128);
                if ( !*(_QWORD *)(v159 + 128) )
                  *(_QWORD *)(v159 + 136) = v158;
                *(_QWORD *)(v159 + 128) = v158;
              }
              v163 = *(_QWORD *)(v159 + 1168) + 1LL;
              ++*(_QWORD *)(v159 + 8);
              v164 = *(SOS_ObjectStore **)(v159 + 32);
              if ( !*((_BYTE *)v164 + 5820) && v163 >= 0x20 )
              {
                PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v164, (struct SList *)v158);
                v166 = *(_QWORD *)(v159 + 128);
                v167 = *(_QWORD **)(v159 + 136);
                if ( v167 != (_QWORD *)(v159 + 128) && v167 )
                {
                  *v167 = *(_QWORD *)(v159 + 8LL * PoolIdForObject + 1184);
                  *(_QWORD *)(v159 + 8LL * PoolIdForObject + 1184) = v166;
                }
                *(_QWORD *)(v159 + 128) = 0;
                *(_QWORD *)(v159 + 136) = v159 + 128;
                v163 = 0;
                v168 = 1LL << PoolIdForObject;
                v169 = *(_QWORD *)(v159 + 1696);
                if ( (v168 & v169) == 0 )
                  *(_QWORD *)(v159 + 1696) = v169 | v168;
              }
              *(_QWORD *)(v159 + 1168) = v163;
              if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
              {
                v170 = rand();
                if ( v170 == 5 * (v170 / 5) )
                  Spinlock<34,1,268435714>::UpdateStatSnapshot();
              }
              *(_QWORD *)(v159 + 40) = 0;
              v3 = this;
            }
          }
          else
          {
            v154 = (ISOSHost_TaskImpl *)(v143 - 1);
            if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
            {
              VirtualFree(v154, 0, 0x8000u);
            }
            else if ( v143 != (__int64 *)8 )
            {
              v155 = 1;
              goto LABEL_440;
            }
          }
        }
LABEL_413:
        *((_QWORD *)v3 + 448) = 0;
        LODWORD(v35) = v182;
      }
LABEL_204:
      v6 = v35;
      v271 = v35;
      goto LABEL_79;
    }
    v46 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v47 = *(_QWORD *)(v46 + 256);
    if ( !v47 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v47 = *(_QWORD *)(v46 + 256);
    }
    v48 = *(_QWORD **)(v47 + 600);
    v49 = 0;
    v50 = v48 + 57;
    do
    {
      v51 = *v50;
      if ( *v50 )
      {
        v124 = MemoryPoolManager::GetPool(v49);
        SOS_MemoryPool::TransferMemory(v124, v51 / 0x2000, 6);
        v48[54] -= v51;
        *v50 -= v51;
        v48[56] -= v51;
      }
      ++v49;
      ++v50;
    }
    while ( v49 < 0x40 );
LABEL_88:
    v43 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v44 = *(_QWORD *)(v43 + 256);
    if ( !v44 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v44 = *(_QWORD *)(v43 + 256);
    }
    v45 = *(void **)(v44 + 496);
    v3 = this;
    v7 = v270;
    if ( v45 )
    {
      operator delete[](v45);
      *(_QWORD *)(v44 + 496) = 0;
    }
  }
}

```

## disassembly

```asm
0x10040ac50  mov     rax, rsp
0x10040ac53  mov     [rax+10h], rdx
0x10040ac57  mov     [rax+8], rcx
0x10040ac5b  push    rbp
0x10040ac5c  push    rbx
0x10040ac5d  push    rsi
0x10040ac5e  push    rdi
0x10040ac5f  push    r12
0x10040ac61  push    r13
0x10040ac63  push    r14
0x10040ac65  push    r15
0x10040ac67  lea     rbp, [rax-0D28h]
0x10040ac6e  sub     rsp, 0DE8h
0x10040ac75  mov     [rbp+0D20h+var_D10], 0FFFFFFFFFFFFFFFEh
0x10040ac7d  movaps  xmmword ptr [rax-58h], xmm6
0x10040ac81  movaps  xmmword ptr [rax-68h], xmm7
0x10040ac85  movaps  xmmword ptr [rax-78h], xmm8
0x10040ac8a  movaps  xmmword ptr [rax-88h], xmm9
0x10040ac92  mov     rsi, rdx
0x10040ac95  mov     r13, rcx
0x10040ac98  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040ac9f  cmp     dword ptr [rax], 0
0x10040aca2  jz      loc_1016DA19F
0x10040aca8  lea     rcx, [rbp+0D20h+PerformanceCount]; lpPerformanceCount
0x10040acac  call    cs:__imp_QueryPerformanceCounter
0x10040acb2  mov     r8, qword ptr [rbp+0D20h+PerformanceCount]
0x10040acb6  jmp     short loc_10040ACB9
0x10040acb9  mov     r9, 346DC5D63886594Bh
0x10040acc3  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040acca  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x10040acce  jnz     loc_1016DA1AD
0x10040acd4  mov     dword ptr [rsp+0E20h+var_DC0], 0FFFFFFFFh
0x10040acdc  cmp     dword ptr [rax], 0
0x10040acdf  jz      loc_1016DA1E1
0x10040ace5  jmp     short loc_10040ACE8
0x10040ace8  lea     rcx, [rbp+0D20h+var_D90]; lpPerformanceCount
0x10040acec  call    cs:__imp_QueryPerformanceCounter
0x10040acf2  mov     rcx, qword ptr [rbp+0D20h+var_D90]
0x10040acf6  mov     r9, 346DC5D63886594Bh
0x10040ad00  jmp     short loc_10040AD03
0x10040ad03  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x10040ad07  jnz     loc_1016DA1EF
0x10040ad0d  mov     [rsp+0E20h+var_DC8], rcx
0x10040ad12  jmp     short loc_10040AD15
0x10040ad15  xor     r14d, r14d
0x10040ad18  mov     r12d, r14d
0x10040ad1b  mov     [rbp+0D20h+arg_18], r14d
0x10040ad22  mov     r15d, 0FFFFFFFFh
0x10040ad28  mov     [rbp+0D20h+arg_10], r15d
0x10040ad2f  mov     edi, r14d
0x10040ad32  mov     [rbp+0D20h+var_D38], 4000B8h
0x10040ad39  mov     [rbp+0D20h+var_D30], r14
0x10040ad3d  mov     [rbp+0D20h+var_D20], r14
0x10040ad41  mov     [rbp+0D20h+var_D28], r14
0x10040ad45  mov     [rbp+0D20h+var_D18], r14
0x10040ad49  mov     rax, cs:qword_10317B628
0x10040ad50  add     rax, 1280h
0x10040ad56  mov     [rbp+0D20h+var_D00], rax
0x10040ad5a  mov     [rbp+0D20h+var_CF8], r14d
0x10040ad5e  lea     rcx, [rbp+0D20h+var_D00]
0x10040ad62  call    ?Reset@Iterator@?$DescriptorAllocator@UBUF@@$0BA@@@QEAAXXZ; DescriptorAllocator<BUF,16>::Iterator::Reset(void)
0x10040ad67  mov     [rbp+0D20h+var_CC8], r14d
0x10040ad6b  mov     [rbp+0D20h+var_CC4], 1
0x10040ad72  xor     eax, eax
0x10040ad74  lock cmpxchg [r13+538h], rsi
0x10040ad7d  jnz     short loc_10040ADE7
0x10040ad7f  mov     rcx, [r13+518h]
0x10040ad86  call    cs:__imp_?IsNotificationInterfaceSet@MemoryClerkInternal@@QEBAHXZ; MemoryClerkInternal::IsNotificationInterfaceSet(void)
0x10040ad8c  test    eax, eax
0x10040ad8e  jnz     short loc_10040ADA4
0x10040ad90  lea     rdx, [r13+540h]
0x10040ad97  mov     rcx, [r13+518h]
0x10040ad9e  call    cs:__imp_?SetNotificationInterface@MemoryClerkInternal@@QEAAXPEAVNotificationInterface@1@@Z; MemoryClerkInternal::SetNotificationInterface(MemoryClerkInternal::NotificationInterface *)
0x10040ada4  mov     rax, cs:__imp_?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A; NodeManager SOS_PublicGlobals::sm_NodeManager
0x10040adab  mov     rbx, [rax+28h]
0x10040adaf  test    rbx, rbx
0x10040adb2  jz      short loc_10040ADBF
0x10040adb4  test    byte ptr [rbx+620h], 10h
0x10040adbb  cmovnz  rbx, r14
0x10040adbf  lea     rdx, [r13+560h]
0x10040adc6  lea     rcx, [rbx+3B0h]
0x10040adcd  call    cs:__imp_?AddMemoryBrokerClerk@ResourceMonitor@@QEAAXPEAVMemoryBrokerClerk@@@Z; ResourceMonitor::AddMemoryBrokerClerk(MemoryBrokerClerk *)
0x10040add3  lea     rdx, [r13+548h]
0x10040adda  lea     rcx, [rbx+3B0h]
0x10040ade1  call    cs:__imp_?AddExternalCache@ResourceMonitor@@QEAAXPEAVExternalCache@@@Z; ResourceMonitor::AddExternalCache(ExternalCache *)
0x10040ade7  mov     rax, [r13+538h]
0x10040adee  mov     [rsp+0E20h+var_DA8], rax
0x10040adf3  mov     dword ptr [rsi+48h], 1
0x10040adfa  mov     ecx, r14d
0x10040adfd  nop     dword ptr [rax]
0x10040ae00  mov     eax, ecx
0x10040ae02  shl     rax, 0Ah
0x10040ae06  add     rax, 9E98h
0x10040ae0c  add     rax, r13
0x10040ae0f  cmp     rsi, rax
0x10040ae12  jz      loc_1016DA230
0x10040ae18  inc     ecx
0x10040ae1a  cmp     ecx, 40h ; '@'
0x10040ae1d  jb      short loc_10040AE00
0x10040ae1f  jmp     short loc_10040AE22
0x10040ae22  mov     rdx, gs:58h
0x10040ae2b  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040ae32  mov     ecx, [rax]
0x10040ae34  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040ae3b  mov     ebx, [rax]
0x10040ae3d  add     rbx, [rdx+rcx*8]
0x10040ae41  mov     rax, [rbx+100h]
0x10040ae48  test    rax, rax
0x10040ae4b  jnz     short loc_10040AE5C
0x10040ae4d  xor     ecx, ecx
0x10040ae4f  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10040ae55  mov     rax, [rbx+100h]
0x10040ae5c  mov     rax, [rax+260h]
0x10040ae63  test    byte ptr [rax+13F0h], 2
0x10040ae6a  jz      short loc_10040AEE5
0x10040ae6c  mov     rcx, rsi
0x10040ae6f  sub     rcx, [r13+9D80h]
0x10040ae76  mov     rax, 0CCCCCCCCCCCCCCCDh
0x10040ae80  mul     rcx
0x10040ae83  shr     rdx, 6
0x10040ae87  mov     rcx, cs:__imp_?sm_NodeManager@SOS_PublicGlobals@@2VNodeManager@@A; NodeManager SOS_PublicGlobals::sm_NodeManager
0x10040ae8e  mov     r8d, 8
0x10040ae94  cmp     [rcx+20h], r8d
0x10040ae98  cmovb   r8d, [rcx+20h]
0x10040ae9d  mov     rax, cs:__imp_?SOS_OS_NumberOfMemoryNodeInfos@@3KA; ulong SOS_OS_NumberOfMemoryNodeInfos
0x10040aea4  mov     r9, [rcx+20h]
0x10040aea8  mov     ecx, [rax]
0x10040aeaa  cmp     r9, rcx
0x10040aead  cmovle  r9d, ecx
0x10040aeb1  add     r9d, r8d
0x10040aeb4  add     r9d, edx
0x10040aeb7  mov     rdx, gs:58h
0x10040aec0  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040aec7  mov     ecx, [rax]
0x10040aec9  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040aed0  mov     eax, [rax]
0x10040aed2  add     rax, [rdx+rcx*8]
0x10040aed6  mov     rax, [rax+8]
0x10040aeda  mov     rcx, [rax+60h]
0x10040aede  mov     [rcx+4E0h], r9d
0x10040aee5  movsd   xmm7, qword ptr cs:__xmm@80000000000000008000000000000000
0x10040aeed  movsd   xmm9, cs:__real@3fa999999999999a
0x10040aef6  movsd   xmm8, cs:__real@4202a05f20000000
0x10040aeff  movsd   xmm6, cs:__real@43e0000000000000
0x10040af07  nop     word ptr [rax+rax+00000000h]
0x10040af10  mov     rdx, gs:58h
0x10040af19  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040af20  mov     ecx, [rax]
0x10040af22  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040af29  mov     esi, [rax]
0x10040af2b  add     rsi, [rdx+rcx*8]
0x10040af2f  mov     rbx, [rsi+100h]
0x10040af36  test    rbx, rbx
0x10040af39  jz      loc_1016DA23F
0x10040af3f  mov     rcx, [rbx+1F0h]
0x10040af46  test    rcx, rcx
0x10040af49  jnz     loc_1016DA254
0x10040af4f  mov     rdx, gs:58h
0x10040af58  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10040af5f  mov     ecx, [rax]
0x10040af61  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10040af68  mov     ebx, [rax]
0x10040af6a  add     rbx, [rdx+rcx*8]
0x10040af6e  mov     rax, [rbx+100h]
0x10040af75  test    rax, rax
0x10040af78  jz      loc_1016DA267
0x10040af7e  movzx   ecx, byte ptr [r13+6Ch]
0x10040af83  mov     rdx, [r13+60h]
0x10040af87  mov     r14d, [rax+4Ch]
0x10040af8b  shl     r14, cl
0x10040af8e  add     r14, rdx
0x10040af91  mov     [rsp+0E20h+var_DD0], r14
0x10040af96  cmp     byte ptr [r14+19h], 0
0x10040af9b  jz      loc_1016DA27C
0x10040afa1  cmp     r15d, 0FFFFFFFFh
0x10040afa5  jz      short loc_10040AFB5
0x10040afa7  movzx   eax, byte ptr [r14+18h]
0x10040afac  cmp     eax, r15d
0x10040afaf  jnz     loc_1016DA28B
0x10040afb5  movzx   r15d, byte ptr [r14+18h]
0x10040afba  shl     r15, 0Ah
0x10040afbe  add     r15, 9E00h
0x10040afc5  add     r15, r13
0x10040afc8  mov     [rbp+0D20h+var_D78], r15
0x10040afcc  mov     rsi, [rbp+0D20h+arg_8]
0x10040afd3  mov     rax, [rsi+38h]
0x10040afd7  test    rax, rax
0x10040afda  jnz     loc_1016DA2BB
0x10040afe0  mov     rax, [rsi+40h]
0x10040afe4  test    rax, rax
0x10040afe7  jz      loc_10040B110
0x10040afed  prefetchw byte ptr [rsi+40h]
0x10040aff1  xor     ecx, ecx
0x10040aff3  nop     dword ptr [rax+00h]
0x10040aff7  nop     word ptr [rax+rax+00000000h]
0x10040b000  mov     rbx, [rsi+40h]
0x10040b004  mov     rax, rbx
0x10040b007  lock cmpxchg [rsi+40h], rcx
0x10040b00d  jnz     short loc_10040B000
0x10040b00f  test    rbx, rbx
0x10040b012  jz      loc_10040B0EF
0x10040b018  xor     r15d, r15d
0x10040b01b  lea     r12d, [r15+1]
0x10040b01f  lea     r14, ?WritePageCompletion@BPool@@CAXPEAVSOS_IOCompRequest@@@Z; BPool::WritePageCompletion(SOS_IOCompRequest *)
0x10040b026  nop     word ptr [rax+rax+00000000h]
0x10040b030  mov     rsi, rbx
0x10040b033  mov     rcx, rbx
0x10040b036  mov     rbx, [rbx+8]
0x10040b03a  mov     edi, r12d
0x10040b03d  test    rbx, rbx
0x10040b040  jz      short loc_10040B079
0x10040b042  cmp     edi, 40h ; '@'
0x10040b045  jnb     short loc_10040B079
0x10040b047  mov     rax, [rcx+90h]
0x10040b04e  cmp     [rbx+90h], rax
0x10040b055  jnz     short loc_10040B079
0x10040b057  mov     eax, [rcx+70h]
0x10040b05a  inc     eax
0x10040b05c  movzx   edx, word ptr [rcx+74h]
0x10040b060  cmp     [rbx+70h], eax
0x10040b063  jnz     short loc_10040B079
0x10040b065  cmp     [rbx+74h], dx
0x10040b069  jnz     short loc_10040B079
0x10040b06b  mov     rcx, rbx
0x10040b06e  mov     rbx, [rbx+8]
0x10040b072  inc     edi
0x10040b074  test    rbx, rbx
0x10040b077  jnz     short loc_10040B042
0x10040b079  mov     [rcx+8], r15
0x10040b07d  mov     rdx, [rsi+90h]
0x10040b084  mov     r9d, r12d
0x10040b087  mov     r8d, edi
0x10040b08a  mov     rdx, [rdx+6B0h]
0x10040b091  mov     rcx, r13
0x10040b094  call    ?GetGroupForBackgroundWrites@BPool@@AEAAPEAVSOS_ResourceGroup@@PEAVDBTABLE@@IW4WM_Opt@1@@Z; BPool::GetGroupForBackgroundWrites(DBTABLE *,uint,BPool::WM_Opt)
0x10040b099  mov     [rbp+0D20h+var_D80], rax
0x10040b09d  lea     r9, [rsi+70h]; struct PageId *
0x10040b0a1  mov     [rsp+40h], r15; void *
0x10040b0a6  mov     [rsp+0E20h+var_DE8], r15; void (*)(struct SOS_IOCompRequest *)
0x10040b0ab  mov     [rsp+0E20h+var_DF0], rax; struct SOS_ResourceGroup *
0x10040b0b0  mov     [rsp+0E20h+var_DF8], rsi; void *
0x10040b0b5  mov     [rsp+0E20h+var_E00], r14; void (*)(struct SOS_IOCompRequest *)
0x10040b0ba  mov     r8d, edi; unsigned int
0x10040b0bd  mov     rdx, rsi; struct BUF *
0x10040b0c0  mov     rcx, [rsi+90h]; this
0x10040b0c7  call    ?GatherWrite@RecoveryUnit@@QEAAXPEAUBUF@@IAEBVPageId@@P6AXPEAVSOS_IOCompRequest@@@ZPEAXPEAVSOS_ResourceGroup@@34@Z; RecoveryUnit::GatherWrite(BUF *,uint,PageId const &,void (*)(SOS_IOCompRequest *),void *,SOS_ResourceGroup *,void (*)(SOS_IOCompRequest *),void *)
0x10040b0cc  nop
0x10040b0cd  lea     rcx, [rbp+0D20h+var_D80]; this
0x10040b0d1  call    ?UnhookAndRelease@SOS_AutoReleaseResourceGroup@@QEAAXXZ; SOS_AutoReleaseResourceGroup::UnhookAndRelease(void)
0x10040b0d6  test    rbx, rbx
0x10040b0d9  jnz     loc_10040B030
0x10040b0df  mov     r14, [rsp+0E20h+var_DD0]
0x10040b0e4  mov     r15, [rbp+0D20h+var_D78]
0x10040b0e8  mov     r12d, [rbp+0D20h+arg_18]
0x10040b0ef  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x10040b0f6  cmp     dword ptr [rax], 0
0x10040b0f9  jz      loc_1016DA3B2
0x10040b0ff  lea     rcx, [rbp+0D20h+var_D70]; lpPerformanceCount
0x10040b103  call    cs:__imp_QueryPerformanceCounter
0x10040b109  mov     rdi, qword ptr [rbp+0D20h+var_D70]
0x10040b10d  jmp     short loc_10040B110
0x10040b110  mov     rdx, r14; struct BufferPartition *
0x10040b113  mov     rcx, r13; this
0x10040b116  call    ?ShouldAdvanceClock@BPool@@AEBAHAEBVBufferPartition@@@Z; BPool::ShouldAdvanceClock(BufferPartition const &)
0x10040b11b  test    eax, eax
0x10040b11d  jz      short loc_10040B132
0x10040b11f  mov     rdx, r15; struct NumaNode *
0x10040b122  mov     rcx, r13; this
0x10040b125  call    ?ShouldShrink@BPool@@AEBAHAEBVNumaNode@@@Z; BPool::ShouldShrink(NumaNode const &)
0x10040b12a  test    eax, eax
0x10040b12c  jnz     loc_1016DA3C0
0x10040b132  xor     edx, edx
0x10040b134  mov     esi, edx
0x10040b136  movzx   ecx, byte ptr [r14+18h]
0x10040b13b  shl     rcx, 0Ah
0x10040b13f  mov     rax, [rcx+r13+9EF0h]
0x10040b147  shr     rax, 2
0x10040b14b  cmp     [rcx+r13+9F00h], rax
0x10040b153  ja      loc_1016DA3C5
0x10040b159  test    byte ptr [r13+24h], 1
0x10040b15e  jnz     loc_1016DA4E9
0x10040b164  mov     edx, 0FFFFFFFFh
0x10040b169  mov     rsi, [rbp+0D20h+arg_8]
0x10040b170  cmp     [rsp+0E20h+var_DA8], rsi
0x10040b175  mov     eax, 3E8h
0x10040b17a  cmovz   edx, eax
0x10040b17d  lea     rcx, [rsi+8]
0x10040b181  mov     byte ptr [rsp+0E20h+var_E00], 1
0x10040b186  xor     r9d, r9d
0x10040b189  lea     r8, [rbp+0D20h+var_D38]
0x10040b18d  call    cs:__imp_?Wait@WaitableBase@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@W4SOS_SYNC_WAIT_OPTIONS@@_N@Z; WaitableBase::Wait(ulong,SOS_WaitInfo const *,SOS_SYNC_WAIT_OPTIONS,bool)
0x10040b193  mov     ebx, eax
0x10040b195  mov     rdx, r14; struct BufferPartition *
0x10040b198  mov     rcx, r13; this
0x10040b19b  call    ?ShouldAdvanceClock@BPool@@AEBAHAEBVBufferPartition@@@Z; BPool::ShouldAdvanceClock(BufferPartition const &)
0x10040b1a0  test    eax, eax
0x10040b1a2  jz      short loc_10040B1BA
0x10040b1a4  mov     rdx, r15; struct NumaNode *
0x10040b1a7  mov     rcx, r13; this
0x10040b1aa  call    ?ShouldShrink@BPool@@AEBAHAEBVNumaNode@@@Z; BPool::ShouldShrink(NumaNode const &)
  ... truncated ...
```

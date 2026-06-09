# BlobAccess_Init(void)

- ea: `0x1019f7d80`
- end: `0x1019f977c`
- name: `?BlobAccess_Init@@YAHXZ`
- size: `6652`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x101ba9540`

## callees

- `0x1004162a0`
- `0x10047b3f0`
- `0x1004c37b0`
- `0x1004c39d0`
- `0x1005486c0`
- `0x1005d8b90`
- `0x10063dc00`
- `0x10065b220`
- `0x1006c5e70`
- `0x1006c6280`
- `0x1006c6560`
- `0x100cdf3a0`
- `0x1019213f0`
- `0x1019f7d80`
- `0x101a3b2c0`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x1019f870c`
- `KERNEL32!VirtualFree` at `0x1019f8c10`
- `KERNEL32!VirtualFree` at `0x1019f965d`
- `KERNEL32!VirtualFree` at `0x1019f870c`
- `KERNEL32!VirtualFree` at `0x1019f8c10`
- `KERNEL32!VirtualFree` at `0x1019f965d`
- `KERNEL32!VirtualProtect` at `0x1019f85b6`
- `KERNEL32!VirtualProtect` at `0x1019f8ac4`
- `KERNEL32!VirtualProtect` at `0x1019f9517`
- `KERNEL32!VirtualProtect` at `0x1019f85b6`
- `KERNEL32!VirtualProtect` at `0x1019f8ac4`
- `KERNEL32!VirtualProtect` at `0x1019f9517`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f8311`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f8364`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f84d1`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f8523`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f881e`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f8871`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f89df`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f8a31`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f9279`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f92cb`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f943d`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f948f`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f8311`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f8364`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f84d1`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f8523`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f881e`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f8871`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f89df`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f8a31`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f9279`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f92cb`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f943d`
- `KERNEL32!QueryPerformanceCounter` at `0x1019f948f`
- `sqldk!?CreateStore@SOS_CacheStore@@SAPEAV1@PEB_WW4SOSHOST_CACHESTORE_TYPE@@K_JPEBUSOSHost_CacheStoreHashTableDescriptor@@P6AXPEAXW4destroy_type@@@ZKW4SOSHOST_MEMOBJ_ID@@PEAVSOS_StoreAndClockAlgorithmControlInterface@@@Z` at `0x1019f96e1`
- `sqldk!?CreateStore@SOS_CacheStore@@SAPEAV1@PEB_WW4SOSHOST_CACHESTORE_TYPE@@K_JPEBUSOSHost_CacheStoreHashTableDescriptor@@P6AXPEAXW4destroy_type@@@ZKW4SOSHOST_MEMOBJ_ID@@PEAVSOS_StoreAndClockAlgorithmControlInterface@@@Z` at `0x1019f96e1`
- `sqldk!?EnqueueTimerTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@P6A?AW4SOS_TIMERRESULT@@PEAXPEAK1@ZP6A?AW43@0@Z30KKPEAVSOSHost@@@Z` at `0x1019f8ce1`
- `sqldk!?EnqueueTimerTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@P6A?AW4SOS_TIMERRESULT@@PEAXPEAK1@ZP6A?AW43@0@Z30KKPEAVSOSHost@@@Z` at `0x1019f90c4`
- `sqldk!?EnqueueTimerTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@P6A?AW4SOS_TIMERRESULT@@PEAXPEAK1@ZP6A?AW43@0@Z30KKPEAVSOSHost@@@Z` at `0x1019f8ce1`
- `sqldk!?EnqueueTimerTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@P6A?AW4SOS_TIMERRESULT@@PEAXPEAK1@ZP6A?AW43@0@Z30KKPEAVSOSHost@@@Z` at `0x1019f90c4`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f7dae`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f7ded`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f7e29`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f7e5b`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f7e7e`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f7eb0`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f7ed3`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f7f0f`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f7f4b`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f7f87`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f7fb9`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f7ff1`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f8029`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f8061`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f80a3`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f80df`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f811b`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f8157`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f8193`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f81cf`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f8c34`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f90df`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f9127`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x1019f972f`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x1019f8d4b`
- `sqldk!?g_pmoGlobal@@3PEAVIMemObj@@EA` at `0x1019f8f12`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1019f866d`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1019f86ac`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1019f8b7d`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1019f8bb6`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1019f95ca`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1019f9603`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1019f82b4`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1019f8474`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1019f87c0`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1019f8981`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1019f921b`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1019f93df`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x1019f86f5`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x1019f8bf9`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x1019f9646`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1019f8325`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1019f84e5`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1019f8832`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1019f89f3`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1019f928d`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1019f9451`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1019f8302`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1019f8354`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1019f84c2`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1019f8513`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1019f880e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1019f8861`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1019f89cf`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1019f8a21`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1019f9269`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1019f92bb`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1019f942d`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1019f947f`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x1019f8226`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x1019f8737`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x1019f9197`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x1019f8226`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x1019f8737`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x1019f9197`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x1019f8420`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x1019f892d`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x1019f938b`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x1019f8420`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x1019f892d`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x1019f938b`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1019f8d83`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1019f8f4f`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1019f8d83`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1019f8f4f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1019f8de1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1019f8fb9`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1019f8de1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1019f8fb9`
- `sqldk!SystemThread_TlsIndex` at `0x1019f82d4`
- `sqldk!SystemThread_TlsIndex` at `0x1019f83b9`
- `sqldk!SystemThread_TlsIndex` at `0x1019f8494`
- `sqldk!SystemThread_TlsIndex` at `0x1019f87e0`
- `sqldk!SystemThread_TlsIndex` at `0x1019f88c6`
- `sqldk!SystemThread_TlsIndex` at `0x1019f89a1`
- `sqldk!SystemThread_TlsIndex` at `0x1019f8c8b`
- `sqldk!SystemThread_TlsIndex` at `0x1019f906e`
- `sqldk!SystemThread_TlsIndex` at `0x1019f923b`
- `sqldk!SystemThread_TlsIndex` at `0x1019f9324`
- `sqldk!SystemThread_TlsIndex` at `0x1019f93ff`
- `sqldk!SystemThread_TlsOffset` at `0x1019f82dd`
- `sqldk!SystemThread_TlsOffset` at `0x1019f83c2`
- `sqldk!SystemThread_TlsOffset` at `0x1019f849d`
- `sqldk!SystemThread_TlsOffset` at `0x1019f87e9`
- `sqldk!SystemThread_TlsOffset` at `0x1019f88cf`
- `sqldk!SystemThread_TlsOffset` at `0x1019f89aa`
- `sqldk!SystemThread_TlsOffset` at `0x1019f8c94`
- `sqldk!SystemThread_TlsOffset` at `0x1019f9077`
- `sqldk!SystemThread_TlsOffset` at `0x1019f9244`
- `sqldk!SystemThread_TlsOffset` at `0x1019f932d`
- `sqldk!SystemThread_TlsOffset` at `0x1019f9408`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1019f8cad`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1019f9090`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1019f8cad`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x1019f9090`
- `sqldk!??_V@YAXPEAX@Z` at `0x1019f8e49`
- `sqldk!??_V@YAXPEAX@Z` at `0x1019f8ed9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1019f9025`
- `sqldk!??_V@YAXPEAX@Z` at `0x1019f8e49`
- `sqldk!??_V@YAXPEAX@Z` at `0x1019f8ed9`
- `sqldk!??_V@YAXPEAX@Z` at `0x1019f9025`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1019f8679`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1019f86b8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1019f8b89`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1019f8bc2`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1019f95d6`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1019f960f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1019f8679`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1019f86b8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1019f8b89`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1019f8bc2`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1019f95d6`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1019f960f`

## string_xrefs

- `0x1019f7dd6`: `BlobAccess`
- `0x1019f7e12`: `BlobAccess`
- `0x1019f7e4e`: `BlobAccess`
- `0x1019f7ea3`: `BlobAccess`
- `0x1019f7ef8`: `BlobAccess`
- `0x1019f7f34`: `BlobAccess`
- `0x1019f7f70`: `BlobAccess`
- `0x1019f7fac`: `BlobAccess`
- `0x1019f80c8`: `BlobAccess`
- `0x1019f8104`: `BlobAccess`
- `0x1019f8140`: `BlobAccess`
- `0x1019f817c`: `BlobAccess`
- `0x1019f81b8`: `BlobAccess`
- `0x1019f81f4`: `BlobAccess`
- `0x1019f9104`: `BlobAccess`
- `0x1019f914c`: `BlobAccess`
- `0x1019f9754`: `BlobAccess`
- `0x1019f7dcf`: `RetryTaskMs`
- `0x1019f7e47`: `LeaseRenewalTaskMs`
- `0x1019f8d71`: `sql\ntdbms\storeng\dfs\manager\blobaccess.cpp`
- `0x1019f8f38`: `sql\ntdbms\storeng\dfs\manager\blobaccess.cpp`
- `0x1019f7fa5`: `ThrottlingMetricsAnalyzerTaskMs`
- `0x1019f7fe4`: `AzureBlobAccessWinHttpConnectTimeoutMs`
- `0x1019f801c`: `AzureBlobAccessWinHttpReceiveTimeoutMs`
- `0x1019f8054`: `AzureBlobAccessWinHttpReceiveResponseTimeoutMs`
- `0x1019f7f2d`: `IOStatsSnapshotTaskMs`
- `0x1019f90fd`: `AADTokenRenewalBufferTimeBeforeExpirationS`
- `0x1019f808c`: `AzureBlobAccessWinHttpSendTimeoutMs`
- `0x1019f9145`: `AADTokenRenewalTaskMs`
- `0x1019f974d`: `S3TempCredentialRenewalBufferTimeBeforeExpirationS`
- `0x1019f96da`: `S3TempCredentialCache`
- `0x1019f8dcf`: `Sql\Ntdbms\iq\common\iqhashtable.h`
- `0x1019f8fa7`: `Sql\Ntdbms\iq\common\iqhashtable.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 BlobAccess_Init(void)
{
  __int64 v0; // rdx
  __int64 v1; // rdx
  __int64 v2; // rdx
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 *v6; // rdi
  DirtyPageMgr *QuadPart; // rbx
  signed __int64 UniqueThread_low; // r14
  __int64 v9; // rsi
  __int64 v10; // r8
  DirtyPageMgr *v11; // rax
  signed __int64 v12; // rcx
  _QWORD *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 *v17; // rcx
  unsigned int v18; // edx
  SOS_Node *v19; // rcx
  __int64 v20; // rbx
  __int64 *v21; // rsi
  __int64 v22; // rdi
  DirtyPageMgr *v23; // rbx
  signed __int64 v24; // r13
  __int64 v25; // r14
  __int64 v26; // r8
  __int64 v27; // rcx
  DirtyPageMgr *v28; // rax
  signed __int64 v29; // rcx
  __int64 *v30; // rcx
  unsigned __int64 v31; // rdx
  SOS_ObjectStore *v32; // rcx
  unsigned int PoolIdForObject; // eax
  __int64 v34; // r9
  __int64 v35; // r10
  _QWORD *v36; // r8
  __int64 v37; // rax
  __int64 v38; // rcx
  int v39; // r8d
  int v40; // r8d
  __int64 *v41; // rdi
  DirtyPageMgr *v42; // rbx
  signed __int64 v43; // r14
  __int64 v44; // rsi
  __int64 v45; // r8
  DirtyPageMgr *v46; // rax
  signed __int64 v47; // rcx
  _QWORD *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // r8
  __int64 v51; // rax
  __int64 *v52; // rcx
  unsigned int v53; // edx
  SOS_Node *v54; // rcx
  __int64 v55; // rbx
  __int64 *v56; // rsi
  __int64 v57; // rdi
  DirtyPageMgr *v58; // rbx
  signed __int64 v59; // r13
  __int64 v60; // r14
  __int64 v61; // r8
  __int64 v62; // rcx
  DirtyPageMgr *v63; // rax
  signed __int64 v64; // rcx
  __int64 *v65; // rcx
  unsigned __int64 v66; // rax
  SOS_ObjectStore *v67; // rcx
  __int64 v68; // r10
  __int64 v69; // r9
  __int64 v70; // rax
  _QWORD *v71; // r8
  __int64 v72; // rcx
  int v73; // r8d
  int v74; // r8d
  int v75; // edi
  __int64 v76; // rbx
  __int64 v77; // rcx
  int v78; // eax
  _QWORD *v79; // rax
  _QWORD *v80; // rbx
  char *v81; // rax
  __int64 v82; // rdx
  char *v83; // rcx
  void *v84; // rcx
  char v85; // al
  char *v87; // rax
  __int64 v88; // rdx
  char *v89; // rcx
  void *v90; // rcx
  int v91; // edi
  __int64 v92; // rbx
  __int64 v93; // rcx
  char v94; // al
  int v95; // ecx
  char v96; // al
  int v97; // edx
  __int64 *v98; // rdi
  DirtyPageMgr *v99; // rbx
  signed __int64 v100; // r14
  __int64 v101; // rsi
  __int64 v102; // r8
  DirtyPageMgr *v103; // rax
  signed __int64 v104; // rcx
  _QWORD *v105; // rcx
  __int64 v106; // rax
  __int64 v107; // r8
  __int64 v108; // rax
  __int64 *v109; // rcx
  unsigned int v110; // edx
  SOS_Node *v111; // rcx
  __int64 v112; // rbx
  __int64 *v113; // rsi
  __int64 v114; // rdi
  DirtyPageMgr *v115; // rbx
  signed __int64 v116; // r12
  __int64 v117; // r14
  __int64 v118; // r8
  __int64 v119; // rcx
  DirtyPageMgr *v120; // rax
  signed __int64 v121; // rcx
  __int64 *v122; // rcx
  unsigned __int64 v123; // rax
  SOS_ObjectStore *v124; // rcx
  unsigned int v125; // eax
  char v126; // r10
  __int64 v127; // r9
  __int64 v128; // rax
  _QWORD *v129; // r8
  __int64 v130; // rcx
  int v131; // r8d
  int v132; // r8d
  __int64 v133; // rcx
  char v134; // al
  int v135; // ecx
  int v136; // [rsp+20h] [rbp-E0h]
  int v137; // [rsp+20h] [rbp-E0h]
  int v138; // [rsp+20h] [rbp-E0h]
  int v139; // [rsp+20h] [rbp-E0h]
  int v140; // [rsp+20h] [rbp-E0h]
  int v141; // [rsp+20h] [rbp-E0h]
  int v142; // [rsp+20h] [rbp-E0h]
  int v143; // [rsp+20h] [rbp-E0h]
  int v144; // [rsp+20h] [rbp-E0h]
  int v145; // [rsp+20h] [rbp-E0h]
  int v146; // [rsp+20h] [rbp-E0h]
  int v147; // [rsp+20h] [rbp-E0h]
  int v148; // [rsp+20h] [rbp-E0h]
  int v149; // [rsp+20h] [rbp-E0h]
  int v150; // [rsp+20h] [rbp-E0h]
  int v151; // [rsp+28h] [rbp-D8h]
  int v152; // [rsp+28h] [rbp-D8h]
  int v153; // [rsp+28h] [rbp-D8h]
  int v154; // [rsp+28h] [rbp-D8h]
  volatile signed __int64 *v155; // [rsp+60h] [rbp-A0h] BYREF
  int v156; // [rsp+68h] [rbp-98h]
  volatile signed __int64 *v157; // [rsp+70h] [rbp-90h] BYREF
  int v158; // [rsp+78h] [rbp-88h]
  volatile signed __int64 *v159; // [rsp+80h] [rbp-80h] BYREF
  int v160; // [rsp+88h] [rbp-78h]
  volatile signed __int32 *v161; // [rsp+90h] [rbp-70h] BYREF
  volatile signed __int32 *v162; // [rsp+98h] [rbp-68h] BYREF
  void *v163; // [rsp+A0h] [rbp-60h]
  void *v164; // [rsp+A8h] [rbp-58h]
  volatile signed __int32 *v165; // [rsp+B0h] [rbp-50h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+B8h] [rbp-48h] BYREF
  LARGE_INTEGER v167; // [rsp+C0h] [rbp-40h] BYREF
  LARGE_INTEGER v168; // [rsp+C8h] [rbp-38h] BYREF
  LARGE_INTEGER v169; // [rsp+D0h] [rbp-30h] BYREF
  LARGE_INTEGER v170; // [rsp+D8h] [rbp-28h] BYREF
  LARGE_INTEGER v171; // [rsp+E0h] [rbp-20h] BYREF
  LARGE_INTEGER v172; // [rsp+E8h] [rbp-18h] BYREF
  LARGE_INTEGER v173; // [rsp+F0h] [rbp-10h] BYREF
  LARGE_INTEGER v174; // [rsp+F8h] [rbp-8h] BYREF
  LARGE_INTEGER v175; // [rsp+100h] [rbp+0h] BYREF
  LARGE_INTEGER v176; // [rsp+108h] [rbp+8h] BYREF
  LARGE_INTEGER v177; // [rsp+110h] [rbp+10h] BYREF
  __int64 v178; // [rsp+118h] [rbp+18h]
  char v179[8]; // [rsp+120h] [rbp+20h] BYREF
  int v180; // [rsp+128h] [rbp+28h]
  int v181; // [rsp+130h] [rbp+30h]
  _QWORD *v182; // [rsp+138h] [rbp+38h]
  char *v183; // [rsp+140h] [rbp+40h]
  __int64 v184; // [rsp+148h] [rbp+48h]
  _QWORD v185[2]; // [rsp+150h] [rbp+50h] BYREF
  char v186; // [rsp+160h] [rbp+60h] BYREF
  __int64 v187; // [rsp+370h] [rbp+270h]
  __int64 v188; // [rsp+378h] [rbp+278h]
  int v189; // [rsp+380h] [rbp+280h] BYREF
  DWORD flOldProtect; // [rsp+3E8h] [rbp+2E8h] BYREF
  DWORD v191; // [rsp+3F0h] [rbp+2F0h] BYREF
  DWORD v192; // [rsp+3F8h] [rbp+2F8h] BYREF

  v178 = -2;
  g_blobAccessTaskSettings = 1000;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, void *, _BYTE, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"BlobAccess",
    L"RetryTaskMs",
    &g_blobAccessTaskSettings,
    0,
    0);
  dword_10317F77C = 1000;
  LOBYTE(v136) = 0;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"BlobAccess",
    L"MaxRetryIOs",
    &dword_10317F77C,
    v136,
    0);
  dword_10317F780 = 1000;
  LOBYTE(v137) = 0;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"BlobAccess",
    L"LeaseRenewalTaskMs",
    &dword_10317F780,
    v137,
    0);
  LOBYTE(v0) = dword_103172574 != 0;
  dword_10317F784 = (*(__int64 (__fastcall **)(struct IServerConfiguration *, __int64))(*(_QWORD *)s_pServerConf + 352LL))(
                      s_pServerConf,
                      v0);
  LOBYTE(v138) = 0;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"BlobAccess",
    L"LeaseDurationS",
    &dword_10317F784,
    v138,
    0);
  LOBYTE(v1) = dword_103172574 != 0;
  dword_10317F788 = (*(__int64 (__fastcall **)(struct IServerConfiguration *, __int64))(*(_QWORD *)s_pServerConf + 360LL))(
                      s_pServerConf,
                      v1);
  LOBYTE(v139) = 0;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"BlobAccess",
    L"LeaseRenewalDurationS",
    &dword_10317F788,
    v139,
    0);
  dword_10317F78C = 30000;
  LOBYTE(v140) = 0;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"BlobAccess",
    L"IOStatsSnapshotTaskMs",
    &dword_10317F78C,
    v140,
    0);
  dword_10317F794 = 300000;
  LOBYTE(v141) = 0;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"BlobAccess",
    L"IOStatsSnapshotNoThrottleMs",
    &dword_10317F794,
    v141,
    0);
  dword_10317F790 = 30000;
  LOBYTE(v142) = 0;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"BlobAccess",
    L"ThrottlingMetricsAnalyzerTaskMs",
    &dword_10317F790,
    v142,
    0);
  LOBYTE(v2) = dword_103172574 != 0;
  LOBYTE(v151) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, __int64, const wchar_t *, void *, int, int))(*(_QWORD *)s_pServerConf + 384LL))(
    s_pServerConf,
    v2,
    L"AzureBlobAccessWinHttpConnectTimeoutMs",
    &g_azureBlobAccessWinHttpTimeoutSettings,
    60000,
    v151);
  LOBYTE(v3) = dword_103172574 != 0;
  LOBYTE(v152) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, __int64, const wchar_t *, int *, int, int))(*(_QWORD *)s_pServerConf + 384LL))(
    s_pServerConf,
    v3,
    L"AzureBlobAccessWinHttpReceiveTimeoutMs",
    &dword_1033ACEAC,
    30000,
    v152);
  LOBYTE(v4) = dword_103172574 != 0;
  LOBYTE(v153) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, __int64, const wchar_t *, char *, int, int))(*(_QWORD *)s_pServerConf + 384LL))(
    s_pServerConf,
    v4,
    L"AzureBlobAccessWinHttpReceiveResponseTimeoutMs",
    byte_1033ACEB0,
    90000,
    v153);
  LOBYTE(v5) = dword_103172574 != 0;
  LOBYTE(v154) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, __int64, const wchar_t *, int *, int, int))(*(_QWORD *)s_pServerConf + 384LL))(
    s_pServerConf,
    v5,
    L"AzureBlobAccessWinHttpSendTimeoutMs",
    &dword_1033ACEB4,
    30000,
    v154);
  g_blobAccessLeaseAndRetrySettings = 3;
  LOBYTE(v143) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, void *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"BlobAccess",
    L"ImmediateRetry",
    &g_blobAccessLeaseAndRetrySettings,
    v143,
    0);
  dword_1033ACEEC = 2;
  LOBYTE(v144) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"BlobAccess",
    L"MaxExponentialBackoff",
    &dword_1033ACEEC,
    v144,
    0);
  dword_1033ACEF0 = 20;
  LOBYTE(v145) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"BlobAccess",
    L"MaxRetry",
    &dword_1033ACEF0,
    v145,
    0);
  dword_1033ACEF4 = 1000;
  LOBYTE(v146) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"BlobAccess",
    L"ThrottlingToleranceDeltaMicrosec",
    &dword_1033ACEF4,
    v146,
    0);
  dword_1033ACEF8 = 1000;
  LOBYTE(v147) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"BlobAccess",
    L"LeaseBreakSleepDurationMS",
    &dword_1033ACEF8,
    v147,
    0);
  dword_1033ACEFC = 10;
  LOBYTE(v148) = 1;
  (*(void (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
    s_pServerConf,
    L"BlobAccess",
    L"LeaseBreakRetryLimit",
    &dword_1033ACEFC,
    v148,
    0);
  v161 = 0;
  v162 = 0;
  if ( (unsigned int)SOS_OS::EnqueueTask(XStoreIoRetryTask2, 0, 2, &v161, -1) )
    return 0;
  v6 = (__int64 *)v161;
  if ( _InterlockedExchangeAdd(v161 + 10, 0xFFFFFFFF) == 1 )
  {
    if ( v6[3] )
    {
      TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v6 + 2);
      goto LABEL_85;
    }
    if ( *((_DWORD *)v6 + 46) == 2 )
    {
      v155 = (volatile signed __int64 *)(v6[20] + 4952);
      v156 = 0;
      QuadPart = 0;
      UniqueThread_low = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)v155 || _InterlockedCompareExchange64(v155, UniqueThread_low, 0) )
      {
        v9 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v10 && *(_QWORD *)(v10 + 272) == v10 )
            v9 = *(_QWORD *)(v10 + 256);
          if ( v9 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&PerformanceCount);
              QuadPart = (DirtyPageMgr *)PerformanceCount.QuadPart;
            }
            else
            {
              QuadPart = MEMORY[0x7FFE0008];
            }
          }
        }
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v155, UniqueThread_low);
        else
          Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v155, v9, UniqueThread_low);
        if ( v9 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v167);
            v11 = (DirtyPageMgr *)v167.QuadPart;
          }
          else
          {
            v11 = MEMORY[0x7FFE0008];
          }
          v12 = v11 - QuadPart;
          if ( v11 < QuadPart )
            v12 = 0;
          *(_QWORD *)(v9 + 3192) += v12;
        }
      }
      v156 = 1;
      v13 = (_QWORD *)v6[1];
      v14 = *v6;
      *(_QWORD *)(v14 + 8) = v13;
      *v13 = v14;
      v6[1] = 0;
      *v6 = 0;
      SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(&v155);
    }
    v15 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    if ( v15 )
    {
      if ( *(_QWORD *)(v15 + 272) == v15 )
      {
        v16 = *(_QWORD *)(v15 + 256);
        if ( v16 )
        {
          if ( *(__int64 **)(v16 + 528) == v6 )
          {
            v17 = v6 - 1;
            if ( !v6 )
              v17 = 0;
            v18 = 0;
            goto LABEL_84;
          }
        }
      }
    }
    v19 = (SOS_Node *)v6[21];
    if ( v19 && *((_QWORD *)v19 + 30) && !SOS_Node::IsTaskStoreDisabled(v19) )
    {
      v20 = *(_QWORD *)(v6[21] + 240);
      v21 = v6 - 1;
      ISOSHost_TaskImpl::`scalar deleting destructor'((ISOSHost_TaskImpl *)(v6 - 1), 0);
      v22 = *(_QWORD *)(v20 + 2016);
      v23 = 0;
      v24 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)(v22 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v22 + 40), v24, 0) )
      {
        v25 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v26 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v26 && *(_QWORD *)(v26 + 272) == v26 )
            v25 = *(_QWORD *)(v26 + 256);
          if ( v25 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v168);
              v23 = (DirtyPageMgr *)v168.QuadPart;
            }
            else
            {
              v23 = MEMORY[0x7FFE0008];
            }
          }
        }
        v27 = v22 + 40;
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v27, v24);
        else
          Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v27, v25, v24);
        if ( v25 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v169);
            v28 = (DirtyPageMgr *)v169.QuadPart;
          }
          else
          {
            v28 = MEMORY[0x7FFE0008];
          }
          v29 = v28 - v23;
          if ( v28 < v23 )
            v29 = 0;
          *(_QWORD *)(v25 + 3192) += v29;
        }
      }
      if ( *(_QWORD *)(v22 + 8) >= *(_QWORD *)v22 )
      {
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v40 = rand();
          if ( v40 == 5 * (v40 / 5) )
            Spinlock<34,1,268435714>::UpdateStatSnapshot();
        }
        *(_QWORD *)(v22 + 40) = 0;
        (*(void (__fastcall **)(__int64 *))(v22 + 48))(v21);
      }
      else
      {
        if ( *(_BYTE *)(*(_QWORD *)(v22 + 32) + 5820LL) )
        {
          v30 = (__int64 *)(v22 + 16 * ((*(_DWORD *)(v22 + 1176) & 0x3F) + 9LL));
          *v21 = *v30;
          if ( !*v30 )
            v30[1] = (__int64)v21;
          *v30 = (__int64)v21;
          ++*(_QWORD *)(v22 + 1176);
          VirtualProtect(v21, 0x1000u, 1u, &flOldProtect);
        }
        else
        {
          *v21 = *(_QWORD *)(v22 + 128);
          if ( !*(_QWORD *)(v22 + 128) )
            *(_QWORD *)(v22 + 136) = v21;
          *(_QWORD *)(v22 + 128) = v21;
        }
        v31 = *(_QWORD *)(v22 + 1168) + 1LL;
        ++*(_QWORD *)(v22 + 8);
        v32 = *(SOS_ObjectStore **)(v22 + 32);
        if ( !*((_BYTE *)v32 + 5820) && v31 >= 0x20 )
        {
          PoolIdForObject = SOS_ObjectStore::GetPoolIdForObject(v32, (struct SList *)v21);
          v34 = v22 + 8LL * PoolIdForObject;
          v35 = *(_QWORD *)(v22 + 128);
          v36 = *(_QWORD **)(v22 + 136);
          if ( v36 != (_QWORD *)(v22 + 128) && v36 )
          {
            *v36 = *(_QWORD *)(v34 + 1184);
            *(_QWORD *)(v34 + 1184) = v35;
          }
          *(_QWORD *)(v22 + 128) = 0;
          *(_QWORD *)(v22 + 136) = v22 + 128;
          v31 = 0;
          v37 = 1LL << PoolIdForObject;
          v38 = *(_QWORD *)(v22 + 1696);
          if ( (v37 & v38) == 0 )
            *(_QWORD *)(v22 + 1696) = v38 | v37;
        }
        *(_QWORD *)(v22 + 1168) = v31;
        if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
        {
          v39 = rand();
          if ( v39 == 5 * (v39 / 5) )
            Spinlock<34,1,268435714>::UpdateStatSnapshot();
        }
        *(_QWORD *)(v22 + 40) = 0;
      }
    }
    else
    {
      v17 = v6 - 1;
      if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
      {
        VirtualFree(v17, 0, 0x8000u);
        goto LABEL_85;
      }
      if ( v6 != (__int64 *)8 )
      {
        v18 = 1;
LABEL_84:
        ISOSHost_TaskImpl::`scalar deleting destructor'((ISOSHost_TaskImpl *)v17, v18);
      }
    }
  }
LABEL_85:
  if ( (unsigned int)SOS_OS::EnqueueTask(XStoreLeaseRenewalTask2, 0, 2, &v162, -1) )
    return 0;
  v41 = (__int64 *)v162;
  if ( _InterlockedExchangeAdd(v162 + 10, 0xFFFFFFFF) == 1 )
  {
    if ( v41[3] )
    {
      TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v41 + 2);
      goto LABEL_169;
    }
    if ( *((_DWORD *)v41 + 46) == 2 )
    {
      v157 = (volatile signed __int64 *)(v41[20] + 4952);
      v158 = 0;
      v42 = 0;
      v43 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
      if ( *(_DWORD *)v157 || _InterlockedCompareExchange64(v157, v43, 0) )
      {
        v44 = 0;
        if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
        {
          v45 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
          if ( v45 && *(_QWORD *)(v45 + 272) == v45 )
            v44 = *(_QWORD *)(v45 + 256);
          if ( v44 )
          {
            if ( Base_PublicGlobals::sm_invariantTscAvailable )
            {
              QueryPerformanceCounter(&v170);
              v42 = (DirtyPageMgr *)v170.QuadPart;
            }
            else
            {
              v42 = MEMORY[0x7FFE0008];
            }
          }
        }
        if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
          Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v157, v43);
        else
          Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v157, v44, v43);
        if ( v44 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v171);
            v46 = (DirtyPageMgr *)v171.QuadPart;
          }
          else
          {
            v46 = MEMORY[0x7FFE0008];
          }
          v47 = v46 - v42;
          if ( v46 < v42 )
            v47 = 0;
          *(_QWORD *)(v44 + 3192) += v47;
        }
      }
      v158 = 1;
      v48 = (_QWORD *)v41[1];
      v49 = *v41;
      *(_QWORD *)(v49 + 8) = v48;
      *v48 = v49;
      v41[1] = 0;
      *v41 = 0;
      SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(&v157);
    }
    v50 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    if ( v50 )
    {
      if ( *(_QWORD *)(v50 + 272) == v50 )
      {
        v51 = *(_QWORD *)(v50 + 256);
        if ( v51 )
        {
          if ( *(__int64 **)(v51 + 528) == v41 )
          {
            v52 = v41 - 1;
            if ( !v41 )
              v52 = 0;
            v53 = 0;
            goto LABEL_168;
          }
        }
      }
    }
    v54 = (SOS_Node *)v41[21];
    if ( !v54 || !*((_QWORD *)v54 + 30) || SOS_Node::IsTaskStoreDisabled(v54) )
    {
      v52 = v41 - 1;
      if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
      {
        VirtualFree(v52, 0, 0x8000u);
        goto LABEL_169;
      }
      if ( v41 == (__int64 *)8 )
        goto LABEL_169;
      v53 = 1;
LABEL_168:
      ISOSHost_TaskImpl::`scalar deleting destructor'((ISOSHost_TaskImpl *)v52, v53);
      goto LABEL_169;
    }
    v55 = *(_QWORD *)(v41[21] + 240);
    v56 = v41 - 1;
    ISOSHost_TaskImpl::`scalar deleting destructor'((ISOSHost_TaskImpl *)(v41 - 1), 0);
    v57 = *(_QWORD *)(v55 + 2016);
    v58 = 0;
    v59 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)(v57 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v57 + 40), v59, 0) )
    {
      v60 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v61 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v61 && *(_QWORD *)(v61 + 272) == v61 )
          v60 = *(_QWORD *)(v61 + 256);
        if ( v60 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v172);
            v58 = (DirtyPageMgr *)v172.QuadPart;
          }
          else
          {
            v58 = MEMORY[0x7FFE0008];
          }
        }
      }
      v62 = v57 + 40;
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v62, v59);
      else
        Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v62, v60, v59);
      if ( v60 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v173);
          v63 = (DirtyPageMgr *)v173.QuadPart;
        }
        else
        {
          v63 = MEMORY[0x7FFE0008];
        }
        v64 = v63 - v58;
        if ( v63 < v58 )
          v64 = 0;
        *(_QWORD *)(v60 + 3192) += v64;
      }
    }
    if ( *(_QWORD *)(v57 + 8) >= *(_QWORD *)v57 )
    {
      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v74 = rand();
        if ( v74 == 5 * (v74 / 5) )
          Spinlock<34,1,268435714>::UpdateStatSnapshot();
      }
      *(_QWORD *)(v57 + 40) = 0;
      (*(void (__fastcall **)(__int64 *))(v57 + 48))(v56);
    }
    else
    {
      if ( *(_BYTE *)(*(_QWORD *)(v57 + 32) + 5820LL) )
      {
        v65 = (__int64 *)(v57 + 16 * ((*(_DWORD *)(v57 + 1176) & 0x3F) + 9LL));
        *v56 = *v65;
        if ( !*v65 )
          v65[1] = (__int64)v56;
        *v65 = (__int64)v56;
        ++*(_QWORD *)(v57 + 1176);
        VirtualProtect(v56, 0x1000u, 1u, &v191);
      }
      else
      {
        *v56 = *(_QWORD *)(v57 + 128);
        if ( !*(_QWORD *)(v57 + 128) )
          *(_QWORD *)(v57 + 136) = v56;
        *(_QWORD *)(v57 + 128) = v56;
      }
      v66 = *(_QWORD *)(v57 + 1168) + 1LL;
      ++*(_QWORD *)(v57 + 8);
      v67 = *(SOS_ObjectStore **)(v57 + 32);
      if ( !*((_BYTE *)v67 + 5820) && v66 >= 0x20 )
      {
        v68 = SOS_ObjectStore::GetPoolIdForObject(v67, (struct SList *)v56);
        v69 = v57 + 8 * v68;
        v70 = *(_QWORD *)(v57 + 128);
        v71 = *(_QWORD **)(v57 + 136);
        if ( v71 != (_QWORD *)(v57 + 128) && v71 )
        {
          *v71 = *(_QWORD *)(v69 + 1184);
          *(_QWORD *)(v69 + 1184) = v70;
        }
        *(_QWORD *)(v57 + 128) = 0;
        *(_QWORD *)(v57 + 136) = v57 + 128;
        v66 = 0;
        v72 = *(_QWORD *)(v57 + 1696);
        if ( (v72 & (1LL << v68)) == 0 )
          *(_QWORD *)(v57 + 1696) = (1LL << v68) | v72;
      }
      *(_QWORD *)(v57 + 1168) = v66;
      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v73 = rand();
        if ( v73 == 5 * (v73 / 5) )
          Spinlock<34,1,268435714>::UpdateStatSnapshot();
      }
      *(_QWORD *)(v57 + 40) = 0;
    }
  }
LABEL_169:
  if ( dword_103172574 )
    v75 = 1000
        * (*(__int64 (__fastcall **)(struct IServerConfiguration *, _QWORD))(*(_QWORD *)s_pServerConf + 400LL))(
            s_pServerConf,
            (unsigned int)(dword_10317F78C / 1000));
  else
    v75 = dword_10317F78C;
  if ( byte_10316EC3A || (byte_10317AC15 & 0x40) != 0 )
  {
    v76 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v77 = *(_QWORD *)(v76 + 256);
    if ( !v77 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v77 = *(_QWORD *)(v76 + 256);
    }
    if ( (unsigned int)SOS_Node::EnqueueTimerTaskDirectInternal(
                         *(_QWORD *)(v77 + 992),
                         &XStoreIOStatsSnapshotTask,
                         0,
                         0,
                         0,
                         0,
                         v75,
                         0) )
      return 0;
  }
  PerfmonManager::AddInstance((PerfmonManager *)&ResourceStr, 0x32u, L"_Total", 0);
  if ( !byte_1033C1052 )
  {
    byte_1033C1044 = byte_10316EBD3 != 0;
    byte_1033C1052 = 1;
  }
  if ( byte_1033C1044 )
  {
    v78 = 0;
    g_blobAccessLeaseAndRetrySettings = 0;
    if ( !qword_1033C1070 )
    {
      v79 = operator new(0x18u, g_pmoGlobal, 1, "sql\\ntdbms\\storeng\\dfs\\manager\\blobaccess.cpp", 1805, 5u);
      v80 = v79;
      if ( v79 )
      {
        v79[1] = 0;
        *((_DWORD *)v79 + 4) = 0;
      }
      else
      {
        v80 = 0;
      }
      v163 = v80;
      if ( !v80 )
        goto LABEL_198;
      *v80 = g_pmoGlobal;
      v81 = (char *)operator new[](0x4EA60u, g_pmoGlobal, 1, "Sql\\Ntdbms\\iq\\common\\iqhashtable.h", 86, 5u);
      if ( v81 )
      {
        v82 = 10067;
        v83 = v81 + 8;
        do
        {
          *((_QWORD *)v83 - 1) = 0;
          *((_DWORD *)v83 + 4) = 0;
          *((_QWORD *)v83 + 1) = v83;
          *(_QWORD *)v83 = v83;
          v83 += 32;
          --v82;
        }
        while ( v82 );
      }
      else
      {
        v81 = 0;
      }
      v80[1] = v81;
      if ( !v81 )
        goto LABEL_198;
      *((_DWORD *)v80 + 4) = 10067;
      v84 = v163;
      if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&qword_1033C1070, (signed __int64)v80, 0) )
        v84 = 0;
      v163 = v84;
      operator delete[](v84);
      v78 = g_blobAccessLeaseAndRetrySettings;
    }
    if ( (qword_10317F6D8 & 0x20000000) != 0 )
    {
      v180 = 0x10000;
      v181 = 0;
      v182 = v185;
      v183 = &v186;
      v187 = 0;
      v184 = 0;
      v188 = 0;
      v185[0] = &v189;
      v185[1] = 4;
      v189 = v78;
      XeSqlPkg::xstore_io_throttling_handler_initialized::Publish((XeSqlPkg::xstore_io_throttling_handler_initialized *)v179);
    }
  }
  if ( byte_1033C1056 )
  {
    v85 = byte_1033C1055;
  }
  else
  {
    v85 = byte_10316EBD2 != 0;
    byte_1033C1055 = byte_10316EBD2 != 0;
    byte_1033C1056 = 1;
  }
  if ( v85 && !qword_1033C1078 )
  {
    v80 = operator new(0x18u, g_pmoGlobal, 1, "sql\\ntdbms\\storeng\\dfs\\manager\\blobaccess.cpp", 1829, 5u);
    if ( v80 )
    {
      *(_OWORD *)v80 = 0;
      v80[2] = 0;
      v80[1] = 0;
      *((_DWORD *)v80 + 4) = 0;
    }
    else
    {
      v80 = 0;
    }
    v164 = v80;
    if ( v80 )
    {
      *v80 = g_pmoGlobal;
      v87 = (char *)operator new[](0x4EA60u, g_pmoGlobal, 1, "Sql\\Ntdbms\\iq\\common\\iqhashtable.h", 86, 5u);
      if ( v87 )
      {
        v88 = 10067;
        v89 = v87 + 8;
        do
        {
          *((_QWORD *)v89 - 1) = 0;
          *((_DWORD *)v89 + 4) = 0;
          *((_QWORD *)v89 + 1) = v89;
          *(_QWORD *)v89 = v89;
          v89 += 32;
          --v88;
        }
        while ( v88 );
      }
      else
      {
        v87 = 0;
      }
      v80[1] = v87;
      if ( v87 )
      {
        *((_DWORD *)v80 + 4) = 10067;
        v90 = v164;
        if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&qword_1033C1078, (signed __int64)v80, 0) )
          v90 = 0;
        v164 = v90;
        operator delete[](v90);
        goto LABEL_217;
      }
    }
LABEL_198:
    operator delete[](v80);
    return 0;
  }
LABEL_217:
  if ( !byte_1033C1052 )
  {
    byte_1033C1044 = byte_10316EBD3 != 0;
    byte_1033C1052 = 1;
  }
  if ( byte_1033C1044 )
  {
    v91 = dword_10317F790;
    v92 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v93 = *(_QWORD *)(v92 + 256);
    if ( !v93 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v93 = *(_QWORD *)(v92 + 256);
    }
    if ( (unsigned int)SOS_Node::EnqueueTimerTaskDirectInternal(
                         *(_QWORD *)(v93 + 992),
                         &ThrottlingMetricsAnalyzerTask,
                         0,
                         0,
                         0,
                         0,
                         v91,
                         0) )
      return 0;
  }
  if ( !byte_10316E97B )
    goto LABEL_312;
  LOBYTE(v149) = 1;
  v94 = (*(__int64 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, void *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"BlobAccess",
          L"AADTokenRenewalBufferTimeBeforeExpirationS",
          &dword_1031C4760,
          v149,
          0);
  v95 = dword_1031C4760;
  if ( !v94 )
    v95 = 1800;
  dword_1031C4760 = v95;
  LOBYTE(v150) = 1;
  v96 = (*(__int64 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, int *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
          s_pServerConf,
          L"BlobAccess",
          L"AADTokenRenewalTaskMs",
          &dword_1031C4764,
          v150,
          0);
  v97 = dword_1031C4764;
  if ( !v96 )
    v97 = 900000;
  dword_1031C4764 = v97;
  XStoreAADTokenCache::Init((XStoreAADTokenCache *)&dword_1031C4760);
  v165 = 0;
  if ( (unsigned int)SOS_OS::EnqueueTask(XStoreAADTokensRenewalTask, 0, 2, &v165, -1) )
    return 0;
  v98 = (__int64 *)v165;
  if ( _InterlockedExchangeAdd(v165 + 10, 0xFFFFFFFF) != 1 )
    goto LABEL_312;
  if ( v98[3] )
  {
    TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(v98 + 2);
    goto LABEL_312;
  }
  if ( *((_DWORD *)v98 + 46) == 2 )
  {
    v159 = (volatile signed __int64 *)(v98[20] + 4952);
    v160 = 0;
    v99 = 0;
    v100 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)v159 || _InterlockedCompareExchange64(v159, v100, 0) )
    {
      v101 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v102 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v102 && *(_QWORD *)(v102 + 272) == v102 )
          v101 = *(_QWORD *)(v102 + 256);
        if ( v101 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v174);
            v99 = (DirtyPageMgr *)v174.QuadPart;
          }
          else
          {
            v99 = MEMORY[0x7FFE0008];
          }
        }
      }
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(v159, v100);
      else
        Spinlock<11,2,268435714>::SpinToAcquireOptimistic(v159, v101, v100);
      if ( v101 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v175);
          v103 = (DirtyPageMgr *)v175.QuadPart;
        }
        else
        {
          v103 = MEMORY[0x7FFE0008];
        }
        v104 = v103 - v99;
        if ( v103 < v99 )
          v104 = 0;
        *(_QWORD *)(v101 + 3192) += v104;
      }
    }
    v160 = 1;
    v105 = (_QWORD *)v98[1];
    v106 = *v98;
    *(_QWORD *)(v106 + 8) = v105;
    *v105 = v106;
    v98[1] = 0;
    *v98 = 0;
    SpinlockHolder<11,2,268435714>::~SpinlockHolder<11,2,268435714>(&v159);
  }
  v107 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  if ( v107 )
  {
    if ( *(_QWORD *)(v107 + 272) == v107 )
    {
      v108 = *(_QWORD *)(v107 + 256);
      if ( v108 )
      {
        if ( *(__int64 **)(v108 + 528) == v98 )
        {
          v109 = v98 - 1;
          if ( !v98 )
            v109 = 0;
          v110 = 0;
          goto LABEL_311;
        }
      }
    }
  }
  v111 = (SOS_Node *)v98[21];
  if ( v111 && *((_QWORD *)v111 + 30) && !SOS_Node::IsTaskStoreDisabled(v111) )
  {
    v112 = *(_QWORD *)(v98[21] + 240);
    v113 = v98 - 1;
    ISOSHost_TaskImpl::`scalar deleting destructor'((ISOSHost_TaskImpl *)(v98 - 1), 0);
    v114 = *(_QWORD *)(v112 + 2016);
    v115 = 0;
    v116 = LODWORD(NtCurrentTeb()->ClientId.UniqueThread);
    if ( *(_DWORD *)(v114 + 40) || _InterlockedCompareExchange64((volatile signed __int64 *)(v114 + 40), v116, 0) )
    {
      v117 = 0;
      if ( (SOS_PublicGlobals::sm_osStats & 0x84) == 0x84 )
      {
        v118 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
        if ( v118 && *(_QWORD *)(v118 + 272) == v118 )
          v117 = *(_QWORD *)(v118 + 256);
        if ( v117 )
        {
          if ( Base_PublicGlobals::sm_invariantTscAvailable )
          {
            QueryPerformanceCounter(&v176);
            v115 = (DirtyPageMgr *)v176.QuadPart;
          }
          else
          {
            v115 = MEMORY[0x7FFE0008];
          }
        }
      }
      v119 = v114 + 40;
      if ( *((char *)&SOS_PublicGlobals::sm_traceFlags + 199) >= 0 )
        Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(v119, v116);
      else
        Spinlock<34,1,268435714>::SpinToAcquireOptimistic(v119, v117, v116);
      if ( v117 )
      {
        if ( Base_PublicGlobals::sm_invariantTscAvailable )
        {
          QueryPerformanceCounter(&v177);
          v120 = (DirtyPageMgr *)v177.QuadPart;
        }
        else
        {
          v120 = MEMORY[0x7FFE0008];
        }
        v121 = v120 - v115;
        if ( v120 < v115 )
          v121 = 0;
        *(_QWORD *)(v117 + 3192) += v121;
      }
    }
    if ( *(_QWORD *)(v114 + 8) >= *(_QWORD *)v114 )
    {
      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v132 = rand();
        if ( v132 == 5 * (v132 / 5) )
          Spinlock<34,1,268435714>::UpdateStatSnapshot();
      }
      *(_QWORD *)(v114 + 40) = 0;
      (*(void (__fastcall **)(__int64 *))(v114 + 48))(v113);
    }
    else
    {
      if ( *(_BYTE *)(*(_QWORD *)(v114 + 32) + 5820LL) )
      {
        v122 = (__int64 *)(v114 + 16 * ((*(_DWORD *)(v114 + 1176) & 0x3F) + 9LL));
        *v113 = *v122;
        if ( !*v122 )
          v122[1] = (__int64)v113;
        *v122 = (__int64)v113;
        ++*(_QWORD *)(v114 + 1176);
        VirtualProtect(v113, 0x1000u, 1u, &v192);
      }
      else
      {
        *v113 = *(_QWORD *)(v114 + 128);
        if ( !*(_QWORD *)(v114 + 128) )
          *(_QWORD *)(v114 + 136) = v113;
        *(_QWORD *)(v114 + 128) = v113;
      }
      v123 = *(_QWORD *)(v114 + 1168) + 1LL;
      ++*(_QWORD *)(v114 + 8);
      v124 = *(SOS_ObjectStore **)(v114 + 32);
      if ( !*((_BYTE *)v124 + 5820) && v123 >= 0x20 )
      {
        v125 = SOS_ObjectStore::GetPoolIdForObject(v124, (struct SList *)v113);
        v126 = v125;
        v127 = v114 + 8LL * v125;
        v128 = *(_QWORD *)(v114 + 128);
        v129 = *(_QWORD **)(v114 + 136);
        if ( v129 != (_QWORD *)(v114 + 128) && v129 )
        {
          *v129 = *(_QWORD *)(v127 + 1184);
          *(_QWORD *)(v127 + 1184) = v128;
        }
        *(_QWORD *)(v114 + 128) = 0;
        *(_QWORD *)(v114 + 136) = v114 + 128;
        v123 = 0;
        v130 = *(_QWORD *)(v114 + 1696);
        if ( (v130 & (1LL << v126)) == 0 )
          *(_QWORD *)(v114 + 1696) = (1LL << v126) | v130;
      }
      *(_QWORD *)(v114 + 1168) = v123;
      if ( (_BYTE)SOS_PublicGlobals::sm_SpinlockStatSnapshot )
      {
        v131 = rand();
        if ( v131 == 5 * (v131 / 5) )
          Spinlock<34,1,268435714>::UpdateStatSnapshot();
      }
      *(_QWORD *)(v114 + 40) = 0;
    }
    goto LABEL_312;
  }
  v109 = v98 - 1;
  if ( (SOS_Tracing_osTrace & 0x1000) != 0 )
  {
    VirtualFree(v109, 0, 0x8000u);
    goto LABEL_312;
  }
  if ( v98 != (__int64 *)8 )
  {
    v110 = 1;
LABEL_311:
    ISOSHost_TaskImpl::`scalar deleting destructor'((ISOSHost_TaskImpl *)v109, v110);
  }
LABEL_312:
  if ( byte_10316EA0A && (qword_10317B120 & 0x1000000000LL) == 0 )
  {
    if ( !(_QWORD)xmmword_1031C47C0 )
    {
      *(_QWORD *)&xmmword_1031C47C0 = SOS_CacheStore::CreateStore(
                                        L"S3TempCredentialCache",
                                        58,
                                        0x2000,
                                        1,
                                        &dword_1031C47A8,
                                        &S3TempCredentialCacheDestroyRoutine,
                                        0,
                                        447,
                                        0);
      *((_QWORD *)&xmmword_1031C47C0 + 1) = TCacheStore<CacheClockAlgorithm>::CreateMemoryObject(
                                              xmmword_1031C47C0,
                                              0,
                                              448,
                                              2,
                                              8,
                                              128);
      if ( !*((_QWORD *)&xmmword_1031C47C0 + 1) )
      {
        LOBYTE(v133) = 5;
        ex_raise_oom(v133);
      }
      dword_1031C47A0 = 120;
    }
    LOBYTE(v149) = 1;
    v134 = (*(__int64 (__fastcall **)(struct IServerConfiguration *, const wchar_t *, const wchar_t *, void *, int, _QWORD))(*(_QWORD *)s_pServerConf + 520LL))(
             s_pServerConf,
             L"BlobAccess",
             L"S3TempCredentialRenewalBufferTimeBeforeExpirationS",
             &dword_1031C47A0,
             v149,
             0);
    v135 = dword_1031C47A0;
    if ( !v134 )
      v135 = 120;
    dword_1031C47A0 = v135;
  }
  return 1;
}

```

## disassembly

```asm
0x1019f7d80  push    rbp
0x1019f7d82  push    rbx
0x1019f7d83  push    rsi
0x1019f7d84  push    rdi
0x1019f7d85  push    r12
0x1019f7d87  push    r13
0x1019f7d89  push    r14
0x1019f7d8b  push    r15
0x1019f7d8d  lea     rbp, [rsp-298h]
0x1019f7d95  sub     rsp, 398h
0x1019f7d9c  mov     [rbp+2D0h+var_2B8], 0FFFFFFFFFFFFFFFEh
0x1019f7da4  mov     cs:?g_blobAccessTaskSettings@@3UBlobAccessTaskSettings@@A, 3E8h; BlobAccessTaskSettings g_blobAccessTaskSettings
0x1019f7dae  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f7db5  mov     rcx, [rax]
0x1019f7db8  mov     rax, [rcx]
0x1019f7dbb  xor     r13d, r13d
0x1019f7dbe  mov     [rsp+3D0h+var_3A8], r13
0x1019f7dc3  mov     byte ptr [rsp+3D0h+var_3B0], r13b
0x1019f7dc8  lea     r9, ?g_blobAccessTaskSettings@@3UBlobAccessTaskSettings@@A; BlobAccessTaskSettings g_blobAccessTaskSettings
0x1019f7dcf  lea     r8, aRetrytaskms; "RetryTaskMs"
0x1019f7dd6  lea     rdx, aBlobaccess; "BlobAccess"
0x1019f7ddd  call    qword ptr [rax+208h]
0x1019f7de3  mov     cs:dword_10317F77C, 3E8h
0x1019f7ded  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f7df4  mov     rcx, [rax]
0x1019f7df7  mov     rax, [rcx]
0x1019f7dfa  mov     [rsp+3D0h+var_3A8], r13
0x1019f7dff  mov     byte ptr [rsp+3D0h+var_3B0], r13b
0x1019f7e04  lea     r9, dword_10317F77C
0x1019f7e0b  lea     r8, aMaxretryios; "MaxRetryIOs"
0x1019f7e12  lea     rdx, aBlobaccess; "BlobAccess"
0x1019f7e19  call    qword ptr [rax+208h]
0x1019f7e1f  mov     cs:dword_10317F780, 3E8h
0x1019f7e29  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f7e30  mov     rcx, [rax]
0x1019f7e33  mov     rax, [rcx]
0x1019f7e36  mov     [rsp+3D0h+var_3A8], r13
0x1019f7e3b  mov     byte ptr [rsp+3D0h+var_3B0], r13b
0x1019f7e40  lea     r9, dword_10317F780
0x1019f7e47  lea     r8, aLeaserenewalta; "LeaseRenewalTaskMs"
0x1019f7e4e  lea     rdx, aBlobaccess; "BlobAccess"
0x1019f7e55  call    qword ptr [rax+208h]
0x1019f7e5b  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f7e62  mov     rcx, [rax]
0x1019f7e65  mov     rax, [rcx]
0x1019f7e68  cmp     cs:dword_103172574, r13d
0x1019f7e6f  setnz   dl
0x1019f7e72  call    qword ptr [rax+160h]
0x1019f7e78  mov     cs:dword_10317F784, eax
0x1019f7e7e  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f7e85  mov     rcx, [rax]
0x1019f7e88  mov     rax, [rcx]
0x1019f7e8b  mov     [rsp+3D0h+var_3A8], r13
0x1019f7e90  mov     byte ptr [rsp+3D0h+var_3B0], r13b
0x1019f7e95  lea     r9, dword_10317F784
0x1019f7e9c  lea     r8, aLeasedurations; "LeaseDurationS"
0x1019f7ea3  lea     rdx, aBlobaccess; "BlobAccess"
0x1019f7eaa  call    qword ptr [rax+208h]
0x1019f7eb0  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f7eb7  mov     rcx, [rax]
0x1019f7eba  mov     rax, [rcx]
0x1019f7ebd  cmp     cs:dword_103172574, r13d
0x1019f7ec4  setnz   dl
0x1019f7ec7  call    qword ptr [rax+168h]
0x1019f7ecd  mov     cs:dword_10317F788, eax
0x1019f7ed3  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f7eda  mov     rcx, [rax]
0x1019f7edd  mov     rax, [rcx]
0x1019f7ee0  mov     [rsp+3D0h+var_3A8], r13
0x1019f7ee5  mov     byte ptr [rsp+3D0h+var_3B0], r13b
0x1019f7eea  lea     r9, dword_10317F788
0x1019f7ef1  lea     r8, aLeaserenewaldu; "LeaseRenewalDurationS"
0x1019f7ef8  lea     rdx, aBlobaccess; "BlobAccess"
0x1019f7eff  call    qword ptr [rax+208h]
0x1019f7f05  mov     cs:dword_10317F78C, 7530h
0x1019f7f0f  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f7f16  mov     rcx, [rax]
0x1019f7f19  mov     rax, [rcx]
0x1019f7f1c  mov     [rsp+3D0h+var_3A8], r13
0x1019f7f21  mov     byte ptr [rsp+3D0h+var_3B0], r13b
0x1019f7f26  lea     r9, dword_10317F78C
0x1019f7f2d  lea     r8, aIostatssnapsho; "IOStatsSnapshotTaskMs"
0x1019f7f34  lea     rdx, aBlobaccess; "BlobAccess"
0x1019f7f3b  call    qword ptr [rax+208h]
0x1019f7f41  mov     cs:dword_10317F794, 493E0h
0x1019f7f4b  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f7f52  mov     rcx, [rax]
0x1019f7f55  mov     rax, [rcx]
0x1019f7f58  mov     [rsp+3D0h+var_3A8], r13
0x1019f7f5d  mov     byte ptr [rsp+3D0h+var_3B0], r13b
0x1019f7f62  lea     r9, dword_10317F794
0x1019f7f69  lea     r8, aIostatssnapsho_0; "IOStatsSnapshotNoThrottleMs"
0x1019f7f70  lea     rdx, aBlobaccess; "BlobAccess"
0x1019f7f77  call    qword ptr [rax+208h]
0x1019f7f7d  mov     cs:dword_10317F790, 7530h
0x1019f7f87  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f7f8e  mov     rcx, [rax]
0x1019f7f91  mov     rax, [rcx]
0x1019f7f94  mov     [rsp+3D0h+var_3A8], r13
0x1019f7f99  mov     byte ptr [rsp+3D0h+var_3B0], r13b
0x1019f7f9e  lea     r9, dword_10317F790
0x1019f7fa5  lea     r8, aThrottlingmetr; "ThrottlingMetricsAnalyzerTaskMs"
0x1019f7fac  lea     rdx, aBlobaccess; "BlobAccess"
0x1019f7fb3  call    qword ptr [rax+208h]
0x1019f7fb9  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f7fc0  mov     rcx, [rax]
0x1019f7fc3  mov     rax, [rcx]
0x1019f7fc6  cmp     cs:dword_103172574, r13d
0x1019f7fcd  setnz   dl
0x1019f7fd0  mov     byte ptr [rsp+3D0h+var_3A8], 1
0x1019f7fd5  mov     dword ptr [rsp+3D0h+var_3B0], 0EA60h
0x1019f7fdd  lea     r9, ?g_azureBlobAccessWinHttpTimeoutSettings@@3UBlobAccessWinHttpTimeoutSettings@@A; BlobAccessWinHttpTimeoutSettings g_azureBlobAccessWinHttpTimeoutSettings
0x1019f7fe4  lea     r8, aAzureblobacces_24; "AzureBlobAccessWinHttpConnectTimeoutMs"
0x1019f7feb  call    qword ptr [rax+180h]
0x1019f7ff1  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f7ff8  mov     rcx, [rax]
0x1019f7ffb  mov     rax, [rcx]
0x1019f7ffe  cmp     cs:dword_103172574, r13d
0x1019f8005  setnz   dl
0x1019f8008  mov     byte ptr [rsp+3D0h+var_3A8], 1
0x1019f800d  mov     dword ptr [rsp+3D0h+var_3B0], 7530h
0x1019f8015  lea     r9, dword_1033ACEAC
0x1019f801c  lea     r8, aAzureblobacces_17; "AzureBlobAccessWinHttpReceiveTimeoutMs"
0x1019f8023  call    qword ptr [rax+180h]
0x1019f8029  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f8030  mov     rcx, [rax]
0x1019f8033  mov     rax, [rcx]
0x1019f8036  cmp     cs:dword_103172574, r13d
0x1019f803d  setnz   dl
0x1019f8040  mov     byte ptr [rsp+3D0h+var_3A8], 1
0x1019f8045  mov     dword ptr [rsp+3D0h+var_3B0], 15F90h
0x1019f804d  lea     r9, byte_1033ACEB0
0x1019f8054  lea     r8, aAzureblobacces_23; "AzureBlobAccessWinHttpReceiveResponseTi"...
0x1019f805b  call    qword ptr [rax+180h]
0x1019f8061  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f8068  mov     rcx, [rax]
0x1019f806b  mov     rax, [rcx]
0x1019f806e  cmp     cs:dword_103172574, r13d
0x1019f8075  setnz   dl
0x1019f8078  mov     byte ptr [rsp+3D0h+var_3A8], 1
0x1019f807d  mov     dword ptr [rsp+3D0h+var_3B0], 7530h
0x1019f8085  lea     r9, dword_1033ACEB4
0x1019f808c  lea     r8, aAzureblobacces_11; "AzureBlobAccessWinHttpSendTimeoutMs"
0x1019f8093  call    qword ptr [rax+180h]
0x1019f8099  mov     cs:?g_blobAccessLeaseAndRetrySettings@@3UBlobAccessLeaseAndRetrySettings@@A, 3; BlobAccessLeaseAndRetrySettings g_blobAccessLeaseAndRetrySettings
0x1019f80a3  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f80aa  mov     rcx, [rax]
0x1019f80ad  mov     rax, [rcx]
0x1019f80b0  mov     [rsp+3D0h+var_3A8], r13
0x1019f80b5  mov     byte ptr [rsp+3D0h+var_3B0], 1
0x1019f80ba  lea     r9, ?g_blobAccessLeaseAndRetrySettings@@3UBlobAccessLeaseAndRetrySettings@@A; BlobAccessLeaseAndRetrySettings g_blobAccessLeaseAndRetrySettings
0x1019f80c1  lea     r8, aImmediateretry; "ImmediateRetry"
0x1019f80c8  lea     rdx, aBlobaccess; "BlobAccess"
0x1019f80cf  call    qword ptr [rax+208h]
0x1019f80d5  mov     cs:dword_1033ACEEC, 2
0x1019f80df  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f80e6  mov     rcx, [rax]
0x1019f80e9  mov     rax, [rcx]
0x1019f80ec  mov     [rsp+3D0h+var_3A8], r13
0x1019f80f1  mov     byte ptr [rsp+3D0h+var_3B0], 1
0x1019f80f6  lea     r9, dword_1033ACEEC
0x1019f80fd  lea     r8, aMaxexponential; "MaxExponentialBackoff"
0x1019f8104  lea     rdx, aBlobaccess; "BlobAccess"
0x1019f810b  call    qword ptr [rax+208h]
0x1019f8111  mov     cs:dword_1033ACEF0, 14h
0x1019f811b  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f8122  mov     rcx, [rax]
0x1019f8125  mov     rax, [rcx]
0x1019f8128  mov     [rsp+3D0h+var_3A8], r13
0x1019f812d  mov     byte ptr [rsp+3D0h+var_3B0], 1
0x1019f8132  lea     r9, dword_1033ACEF0
0x1019f8139  lea     r8, aMaxretry; "MaxRetry"
0x1019f8140  lea     rdx, aBlobaccess; "BlobAccess"
0x1019f8147  call    qword ptr [rax+208h]
0x1019f814d  mov     cs:dword_1033ACEF4, 3E8h
0x1019f8157  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f815e  mov     rcx, [rax]
0x1019f8161  mov     rax, [rcx]
0x1019f8164  mov     [rsp+3D0h+var_3A8], r13
0x1019f8169  mov     byte ptr [rsp+3D0h+var_3B0], 1
0x1019f816e  lea     r9, dword_1033ACEF4
0x1019f8175  lea     r8, aThrottlingtole; "ThrottlingToleranceDeltaMicrosec"
0x1019f817c  lea     rdx, aBlobaccess; "BlobAccess"
0x1019f8183  call    qword ptr [rax+208h]
0x1019f8189  mov     cs:dword_1033ACEF8, 3E8h
0x1019f8193  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f819a  mov     rcx, [rax]
0x1019f819d  mov     rax, [rcx]
0x1019f81a0  mov     [rsp+3D0h+var_3A8], r13
0x1019f81a5  mov     byte ptr [rsp+3D0h+var_3B0], 1
0x1019f81aa  lea     r9, dword_1033ACEF8
0x1019f81b1  lea     r8, aLeasebreakslee; "LeaseBreakSleepDurationMS"
0x1019f81b8  lea     rdx, aBlobaccess; "BlobAccess"
0x1019f81bf  call    qword ptr [rax+208h]
0x1019f81c5  mov     cs:dword_1033ACEFC, 0Ah
0x1019f81cf  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x1019f81d6  mov     rcx, [rax]
0x1019f81d9  mov     rax, [rcx]
0x1019f81dc  mov     [rsp+3D0h+var_3A8], r13
0x1019f81e1  mov     byte ptr [rsp+3D0h+var_3B0], 1
0x1019f81e6  lea     r9, dword_1033ACEFC
0x1019f81ed  lea     r8, aLeasebreakretr; "LeaseBreakRetryLimit"
0x1019f81f4  lea     rdx, aBlobaccess; "BlobAccess"
0x1019f81fb  call    qword ptr [rax+208h]
0x1019f8201  mov     [rbp+2D0h+var_340], r13
0x1019f8205  mov     [rbp+2D0h+var_338], r13
0x1019f8209  mov     r12, 0FFFFFFFFFFFFFFFFh
0x1019f8210  mov     [rsp+3D0h+var_3B0], r12
0x1019f8215  lea     r9, [rbp+2D0h+var_340]
0x1019f8219  xor     edx, edx
0x1019f821b  lea     r8d, [r13+2]
0x1019f821f  lea     rcx, ?XStoreIoRetryTask2@@YAPEAXPEAX@Z; XStoreIoRetryTask2(void *)
0x1019f8226  call    cs:__imp_?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z; SOS_OS::EnqueueTask(void * (*)(void *),void *,ulong,SOS_Task * *,unsigned __int64)
0x1019f822c  test    eax, eax
0x1019f822e  jnz     loc_1019F8EDF
0x1019f8234  mov     rdi, [rbp+2D0h+var_340]
0x1019f8238  mov     eax, r12d
0x1019f823b  lock xadd [rdi+28h], eax
0x1019f8240  mov     r15d, 1
0x1019f8246  cmp     eax, r15d
0x1019f8249  jnz     loc_1019F8721
0x1019f824f  cmp     [rdi+18h], r13
0x1019f8253  jz      short loc_1019F8263
0x1019f8255  lea     rcx, [rdi+10h]
0x1019f8259  call    ?RemoveAndDestroy@?$TListElem@V?$TList@VSOS_Scheduler@@VSOS_Task@@$0BA@UTListSLock@@@@@@IEAAXXZ; TListElem<TList<SOS_Scheduler,SOS_Task,16,TListSLock>>::RemoveAndDestroy(void)
0x1019f825e  jmp     loc_1019F8721
0x1019f8263  mov     eax, [rdi+0B8h]
0x1019f8269  cmp     eax, 2
0x1019f826c  jnz     loc_1019F83B0
0x1019f8272  mov     rax, [rdi+0A0h]
0x1019f8279  add     rax, 1358h
0x1019f827f  mov     [rsp+3D0h+var_370], rax
0x1019f8284  mov     [rsp+3D0h+var_368], r13d
0x1019f8289  mov     rbx, r13
0x1019f828c  mov     eax, gs:48h
0x1019f8294  mov     r14d, eax
0x1019f8297  mov     rax, [rsp+3D0h+var_370]
0x1019f829c  mov     ecx, [rax]
0x1019f829e  test    ecx, ecx
0x1019f82a0  jnz     short loc_1019F82B4
0x1019f82a2  mov     rcx, [rsp+3D0h+var_370]
0x1019f82a7  xor     eax, eax
0x1019f82a9  lock cmpxchg [rcx], r14
0x1019f82ae  jz      loc_1019F838C
0x1019f82b4  mov     rax, cs:__imp_?sm_osStats@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osStats
0x1019f82bb  mov     ecx, [rax]
0x1019f82bd  and     ecx, 84h
0x1019f82c3  mov     rsi, r13
0x1019f82c6  cmp     cl, 84h
0x1019f82c9  jnz     short loc_1019F8325
0x1019f82cb  mov     rdx, gs:58h
0x1019f82d4  mov     rax, cs:__imp_SystemThread_TlsIndex
0x1019f82db  mov     ecx, [rax]
0x1019f82dd  mov     rax, cs:__imp_SystemThread_TlsOffset
0x1019f82e4  mov     r8d, [rax]
0x1019f82e7  add     r8, [rdx+rcx*8]
0x1019f82eb  jz      short loc_1019F82FD
0x1019f82ed  cmp     [r8+110h], r8
0x1019f82f4  jnz     short loc_1019F82FD
0x1019f82f6  mov     rsi, [r8+100h]
0x1019f82fd  test    rsi, rsi
0x1019f8300  jz      short loc_1019F8325
0x1019f8302  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1019f8309  cmp     [rax], ebx
0x1019f830b  jz      short loc_1019F831D
0x1019f830d  lea     rcx, [rbp+2D0h+PerformanceCount]; lpPerformanceCount
0x1019f8311  call    cs:__imp_QueryPerformanceCounter
0x1019f8317  mov     rbx, qword ptr [rbp+2D0h+PerformanceCount]
0x1019f831b  jmp     short loc_1019F8325
0x1019f831d  mov     rbx, ds:7FFE0008h
0x1019f8325  mov     rax, cs:__imp_?sm_traceFlags@SOS_PublicGlobals@@2PAEA; uchar near * SOS_PublicGlobals::sm_traceFlags
0x1019f832c  mov     rcx, [rsp+3D0h+var_370]
0x1019f8331  cmp     byte ptr [rax+0C7h], 0
0x1019f8338  jge     short loc_1019F8347
0x1019f833a  mov     r8, r14
0x1019f833d  mov     rdx, rsi
0x1019f8340  call    ?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z; Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)
0x1019f8345  jmp     short loc_1019F834F
0x1019f8347  mov     rdx, r14
0x1019f834a  call    ?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z; Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)
0x1019f834f  test    rsi, rsi
0x1019f8352  jz      short loc_1019F838C
0x1019f8354  mov     rax, cs:__imp_?sm_invariantTscAvailable@Base_PublicGlobals@@2HA; int Base_PublicGlobals::sm_invariantTscAvailable
0x1019f835b  cmp     dword ptr [rax], 0
0x1019f835e  jz      short loc_1019F8370
0x1019f8360  lea     rcx, [rbp+2D0h+var_310]; lpPerformanceCount
0x1019f8364  call    cs:__imp_QueryPerformanceCounter
0x1019f836a  mov     rax, qword ptr [rbp+2D0h+var_310]
0x1019f836e  jmp     short loc_1019F8378
0x1019f8370  mov     rax, ds:7FFE0008h
0x1019f8378  mov     rcx, rax
0x1019f837b  sub     rcx, rbx
0x1019f837e  cmp     rax, rbx
0x1019f8381  cmovb   rcx, r13
0x1019f8385  add     [rsi+0C78h], rcx
0x1019f838c  mov     [rsp+3D0h+var_368], r15d
0x1019f8391  mov     rcx, [rdi+8]
0x1019f8395  mov     rax, [rdi]
0x1019f8398  mov     [rax+8], rcx
0x1019f839c  mov     [rcx], rax
  ... truncated ...
```

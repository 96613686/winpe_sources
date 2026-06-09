# TDSSNIClient::AcceptCommon(SNI_Conn *,void *,int)

- ea: `0x10055aee0`
- end: `0x10055b104`
- name: `?AcceptCommon@TDSSNIClient@@SAXPEAVSNI_Conn@@PEAXH@Z`
- size: `548`
- prototype: `void __fastcall(struct SNI_Conn *, void *, int)`
- caller_count: `2`
- callee_count: `33`
- tags: `service_task, broker_com_uri`

## callers

- `0x10055aed0`
- `0x100f6eec0`

## callees

- `0x100401070`
- `0x10041e0c0`
- `0x10041e110`
- `0x10041e190`
- `0x10041e9f0`
- `0x10041f7d0`
- `0x1005508a0`
- `0x10055aee0`
- `0x10055f950`
- `0x100562360`
- `0x100562640`
- `0x100567ff0`
- `0x100725fb0`
- `0x1007978b0`
- `0x1007a1d00`
- `0x1007a2e00`
- `0x1007a70d0`
- `0x1007a72f0`
- `0x1007e01f0`
- `0x1007e0c00`
- `0x1007e0e70`
- `0x100f08630`
- `0x100f731f0`
- `0x100f741e0`
- `0x100f755f0`
- `0x100f75b90`
- `0x100f75e00`
- `0x100f82280`
- `0x100f82380`
- `0x100f844f0`
- `0x100f845c0`
- `0x10100ccd0`
- `0x10100d740`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100f6ef6e`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6efb5`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6f458`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6f4a3`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6f64c`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6f69d`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6f8e7`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6f95e`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6fe5b`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6fea6`
- `KERNEL32!QueryPerformanceCounter` at `0x100f70053`
- `KERNEL32!QueryPerformanceCounter` at `0x100f700a4`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6ef6e`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6efb5`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6f458`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6f4a3`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6f64c`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6f69d`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6f8e7`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6f95e`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6fe5b`
- `KERNEL32!QueryPerformanceCounter` at `0x100f6fea6`
- `KERNEL32!QueryPerformanceCounter` at `0x100f70053`
- `KERNEL32!QueryPerformanceCounter` at `0x100f700a4`
- `KERNEL32!VirtualProtect` at `0x100f6f71c`
- `KERNEL32!VirtualProtect` at `0x100f70123`
- `KERNEL32!VirtualProtect` at `0x100f6f71c`
- `KERNEL32!VirtualProtect` at `0x100f70123`
- `KERNEL32!VirtualFree` at `0x100f6f895`
- `KERNEL32!VirtualFree` at `0x100f7029f`
- `KERNEL32!VirtualFree` at `0x100f6f895`
- `KERNEL32!VirtualFree` at `0x100f7029f`
- `sqldk!?SOS_OS_NumDACCount@@3KA` at `0x100f6f18c`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100f6ef7b`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100f6f465`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100f6f65e`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100f6fe68`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100f70065`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x100f6f87e`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x100f70288`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100f6ef11`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100f6f3f7`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100f6f5eb`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100f6fdfa`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100f6fff2`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x10055b05c`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x100f6f2c0`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10055b003`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f6f7ab`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f6f838`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f6f914`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f6f985`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f701b5`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100f70242`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f6ef5f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f6efa5`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f6f445`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f6f48f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f6f639`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f6f689`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f6f8d3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f6f94a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f6fe48`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f6fe92`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f70040`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100f70090`
- `sqldk!?SelectNodeForGroup@SOS_Node@@SAPEAV1@PEAVSOS_ResourceGroup@@PEAV1@@Z` at `0x100f6fc7c`
- `sqldk!?SelectNodeForGroup@SOS_Node@@SAPEAV1@PEAVSOS_ResourceGroup@@PEAV1@@Z` at `0x100f6fc7c`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x100f6f58b`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x100f6ff92`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x100f6f58b`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x100f6ff92`
- `sqldk!?EnqueueTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@PEAVParam@SOS_Task@@PEAVSOSHost@@PEAPEAV4@PEAPEAX@Z` at `0x10055b0ab`
- `sqldk!?EnqueueTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@PEAVParam@SOS_Task@@PEAVSOSHost@@PEAPEAV4@PEAPEAX@Z` at `0x100f6fca0`
- `sqldk!?EnqueueTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@PEAVParam@SOS_Task@@PEAVSOSHost@@PEAPEAV4@PEAPEAX@Z` at `0x10055b0ab`
- `sqldk!?EnqueueTaskDirectInternal@SOS_Node@@AEAA?AW4SOS_RESULT@@PEAVParam@SOS_Task@@PEAVSOSHost@@PEAPEAV4@PEAPEAX@Z` at `0x100f6fca0`
- `sqldk!SystemThread_TlsIndex` at `0x10055af3b`
- `sqldk!SystemThread_TlsIndex` at `0x100f6ef31`
- `sqldk!SystemThread_TlsIndex` at `0x100f6f417`
- `sqldk!SystemThread_TlsIndex` at `0x100f6f4f2`
- `sqldk!SystemThread_TlsIndex` at `0x100f6f60b`
- `sqldk!SystemThread_TlsIndex` at `0x100f6fe1a`
- `sqldk!SystemThread_TlsIndex` at `0x100f6fef5`
- `sqldk!SystemThread_TlsIndex` at `0x100f70012`
- `sqldk!SystemThread_TlsOffset` at `0x10055af44`
- `sqldk!SystemThread_TlsOffset` at `0x100f6ef3a`
- `sqldk!SystemThread_TlsOffset` at `0x100f6f420`
- `sqldk!SystemThread_TlsOffset` at `0x100f6f4fb`
- `sqldk!SystemThread_TlsOffset` at `0x100f6f614`
- `sqldk!SystemThread_TlsOffset` at `0x100f6fe23`
- `sqldk!SystemThread_TlsOffset` at `0x100f6fefe`
- `sqldk!SystemThread_TlsOffset` at `0x100f7001b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f6eecd`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f6eecd`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f6f005`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f6f7b7`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f6f844`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f6f920`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f6f991`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f701c1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f7024e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f6f005`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f6f7b7`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f6f844`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f6f920`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f6f991`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f701c1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100f7024e`

## pseudocode

```c

```

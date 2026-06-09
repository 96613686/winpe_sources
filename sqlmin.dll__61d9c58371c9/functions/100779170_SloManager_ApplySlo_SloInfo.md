# SloManager::ApplySlo(SloInfo *)

- ea: `0x100779170`
- end: `0x10077ad9c`
- name: `?ApplySlo@SloManager@@QEAAXPEAVSloInfo@@@Z`
- size: `7212`
- prototype: `void __fastcall(SloManager *__hidden this, struct SloInfo *)`
- caller_count: `2`
- callee_count: `28`
- tags: `file_ops, registry_config`

## callers

- `0x100781cd0`
- `0x100781e00`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x1004058c0`
- `0x100405990`
- `0x100405ed0`
- `0x100418690`
- `0x1004fddc0`
- `0x1005666e0`
- `0x10060d810`
- `0x100626050`
- `0x1006c66e0`
- `0x1006c6920`
- `0x1007740e0`
- `0x100774f70`
- `0x100776830`
- `0x100776bd0`
- `0x100779170`
- `0x10077b560`
- `0x10077b920`
- `0x10077bdf0`
- `0x10077c830`
- `0x10077cf30`
- `0x100780a70`
- `0x100780ed0`
- `0x100780f60`
- `0x1007825e0`
- `0x1023aee60`
- `0x1023aef40`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x10077acdb`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x10077acdb`
- `KERNEL32!QueryPerformanceCounter` at `0x100779b02`
- `KERNEL32!QueryPerformanceCounter` at `0x100779b54`
- `KERNEL32!QueryPerformanceCounter` at `0x100779b02`
- `KERNEL32!QueryPerformanceCounter` at `0x100779b54`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100779bca`
- `sqldk!?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A` at `0x100779243`
- `sqldk!?sm_isResourceManagerEnabled@SOS_PublicGlobals@@2HA` at `0x1007791fa`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100779aa5`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100779b16`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100779af3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100779b44`
- `sqldk!?g_dbtableFactory@@3UDBTableFactory@@A` at `0x10077941b`
- `sqldk!?CreatePool@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEBVResourcePoolData@@P6AXPEAVSOS_ResourcePool@@W4RESOBJECT_ACTION@@@ZPEAPEAV4@@Z` at `0x100779779`
- `sqldk!?CreatePool@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEBVResourcePoolData@@P6AXPEAVSOS_ResourcePool@@W4RESOBJECT_ACTION@@@ZPEAPEAV4@@Z` at `0x1007799ca`
- `sqldk!?CreatePool@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEBVResourcePoolData@@P6AXPEAVSOS_ResourcePool@@W4RESOBJECT_ACTION@@@ZPEAPEAV4@@Z` at `0x100779779`
- `sqldk!?CreatePool@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEBVResourcePoolData@@P6AXPEAVSOS_ResourcePool@@W4RESOBJECT_ACTION@@@ZPEAPEAV4@@Z` at `0x1007799ca`
- `sqldk!?AlterPool@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEAVSOS_ResourcePool@@PEBVResourcePoolData@@@Z` at `0x10077abcf`
- `sqldk!?AlterPool@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEAVSOS_ResourcePool@@PEBVResourcePoolData@@@Z` at `0x10077abcf`
- `sqldk!?DropPool@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEAVSOS_ResourcePool@@P6AX0W4RESOBJECT_ACTION@@@Z@Z` at `0x10077a1c5`
- `sqldk!?DropPool@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEAVSOS_ResourcePool@@P6AX0W4RESOBJECT_ACTION@@@Z@Z` at `0x10077a1c5`
- `sqldk!?CreateGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEBVResourceGroupData@@PEAVSOS_ResourcePool@@P6AXPEAVSOS_ResourceGroup@@W4RESOBJECT_ACTION@@PEAX@ZPEAPEAV5@@Z` at `0x100779f36`
- `sqldk!?CreateGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEBVResourceGroupData@@PEAVSOS_ResourcePool@@P6AXPEAVSOS_ResourceGroup@@W4RESOBJECT_ACTION@@PEAX@ZPEAPEAV5@@Z` at `0x10077a07a`
- `sqldk!?CreateGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEBVResourceGroupData@@PEAVSOS_ResourcePool@@P6AXPEAVSOS_ResourceGroup@@W4RESOBJECT_ACTION@@PEAX@ZPEAPEAV5@@Z` at `0x10077a7ac`
- `sqldk!?CreateGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEBVResourceGroupData@@PEAVSOS_ResourcePool@@P6AXPEAVSOS_ResourceGroup@@W4RESOBJECT_ACTION@@PEAX@ZPEAPEAV5@@Z` at `0x100779f36`
- `sqldk!?CreateGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEBVResourceGroupData@@PEAVSOS_ResourcePool@@P6AXPEAVSOS_ResourceGroup@@W4RESOBJECT_ACTION@@PEAX@ZPEAPEAV5@@Z` at `0x10077a07a`
- `sqldk!?CreateGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEBVResourceGroupData@@PEAVSOS_ResourcePool@@P6AXPEAVSOS_ResourceGroup@@W4RESOBJECT_ACTION@@PEAX@ZPEAPEAV5@@Z` at `0x10077a7ac`
- `sqldk!?AlterGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEAVSOS_ResourceGroup@@PEBVResourceGroupData@@PEAVSOS_ResourcePool@@@Z` at `0x10077abe9`
- `sqldk!?AlterGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEAVSOS_ResourceGroup@@PEBVResourceGroupData@@PEAVSOS_ResourcePool@@@Z` at `0x10077ac12`
- `sqldk!?AlterGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEAVSOS_ResourceGroup@@PEBVResourceGroupData@@PEAVSOS_ResourcePool@@@Z` at `0x10077abe9`
- `sqldk!?AlterGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEAVSOS_ResourceGroup@@PEBVResourceGroupData@@PEAVSOS_ResourcePool@@@Z` at `0x10077ac12`
- `sqldk!?DropGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEAVSOS_ResourceGroup@@P6AX0W4RESOBJECT_ACTION@@PEAX@Z@Z` at `0x10077a10c`
- `sqldk!?DropGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEAVSOS_ResourceGroup@@P6AX0W4RESOBJECT_ACTION@@PEAX@Z@Z` at `0x10077a12b`
- `sqldk!?DropGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEAVSOS_ResourceGroup@@P6AX0W4RESOBJECT_ACTION@@PEAX@Z@Z` at `0x10077a10c`
- `sqldk!?DropGroup@SOS_ResourceManager@@QEAA?AW4SOS_RESULT@@PEAVSOS_ResourceGroup@@P6AX0W4RESOBJECT_ACTION@@PEAX@Z@Z` at `0x10077a12b`
- `sqldk!?ApplyPoolProperties@ResourcePoolData@@QEAAXPEBV1@@Z` at `0x10077949c`
- `sqldk!?ApplyPoolProperties@ResourcePoolData@@QEAAXPEBV1@@Z` at `0x10077949c`
- `sqldk!?IsEmpty@SystemAffinity@@QEBAHXZ` at `0x1007795ac`
- `sqldk!?IsEmpty@SystemAffinity@@QEBAHXZ` at `0x1007795d7`
- `sqldk!?IsEmpty@SystemAffinity@@QEBAHXZ` at `0x1007795ac`
- `sqldk!?IsEmpty@SystemAffinity@@QEBAHXZ` at `0x1007795d7`
- `sqldk!?ApplyGroupProperties@ResourceGroupData@@QEAAXPEBV1@@Z` at `0x100779478`
- `sqldk!?ApplyGroupProperties@ResourceGroupData@@QEAAXPEBV1@@Z` at `0x1007794bc`
- `sqldk!?ApplyGroupProperties@ResourceGroupData@@QEAAXPEBV1@@Z` at `0x100779478`
- `sqldk!?ApplyGroupProperties@ResourceGroupData@@QEAAXPEBV1@@Z` at `0x1007794bc`
- `sqldk!??0ResourceViolationConfig@@QEAA@XZ` at `0x1007792b3`
- `sqldk!??0ResourceViolationConfig@@QEAA@XZ` at `0x1007792b3`
- `sqldk!?Destroy@SOS_ResourcePool@@QEAAXXZ` at `0x100779c49`
- `sqldk!?Destroy@SOS_ResourcePool@@QEAAXXZ` at `0x100779cc3`
- `sqldk!?Destroy@SOS_ResourcePool@@QEAAXXZ` at `0x100779dd5`
- `sqldk!?Destroy@SOS_ResourcePool@@QEAAXXZ` at `0x100779e11`
- `sqldk!?Destroy@SOS_ResourcePool@@QEAAXXZ` at `0x10077a27e`
- `sqldk!?Destroy@SOS_ResourcePool@@QEAAXXZ` at `0x10077a2ba`
- `sqldk!?Destroy@SOS_ResourcePool@@QEAAXXZ` at `0x100779c49`
- `sqldk!?Destroy@SOS_ResourcePool@@QEAAXXZ` at `0x100779cc3`
- `sqldk!?Destroy@SOS_ResourcePool@@QEAAXXZ` at `0x100779dd5`
- `sqldk!?Destroy@SOS_ResourcePool@@QEAAXXZ` at `0x100779e11`
- `sqldk!?Destroy@SOS_ResourcePool@@QEAAXXZ` at `0x10077a27e`
- `sqldk!?Destroy@SOS_ResourcePool@@QEAAXXZ` at `0x10077a2ba`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x100779300`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x100779681`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x100779300`
- `sqldk!??0SystemAffinity@@QEAA@XZ` at `0x100779681`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100779c5b`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100779c5b`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x10077a5f2`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x10077a6be`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x10077a5f2`
- `sqldk!?GetErrorReportingManager@@YAAEAVIErrorReportingManager@@XZ` at `0x10077a6be`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10077a8f2`
- `sqldk!?CheckSessionTraceInternal@CSessionTraceFlags@@CAHPEAV1@K@Z` at `0x10077a8f2`
- `sqldk!SystemThread_TlsIndex` at `0x100779ac5`
- `sqldk!SystemThread_TlsIndex` at `0x10077a0a2`
- `sqldk!SystemThread_TlsIndex` at `0x10077a862`
- `sqldk!SystemThread_TlsIndex` at `0x10077a8c3`
- `sqldk!SystemThread_TlsOffset` at `0x100779ace`
- `sqldk!SystemThread_TlsOffset` at `0x10077a0ab`
- `sqldk!SystemThread_TlsOffset` at `0x10077a86b`
- `sqldk!SystemThread_TlsOffset` at `0x10077a8cc`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10077a0c6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10077a886`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10077a0c6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10077a886`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100779bd6`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100779bd6`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x100779c80`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x100779c80`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100779891`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1007798ad`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1007798c9`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100779d09`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100779d21`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100779d39`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a018`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a030`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a048`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a524`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a53c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a554`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a820`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a838`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a850`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100779891`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1007798ad`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1007798c9`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100779d09`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100779d21`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x100779d39`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a018`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a030`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a048`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a524`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a53c`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a554`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a820`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a838`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10077a850`

## string_xrefs

- `0x10077a18a`: `SloManager::ApplySlo() : Unable to delete feature workload resource groups from user pool`
- `0x10077a60a`: `SloMgmt:ApplySlo - m_pSecSGroup2 already exists.`

## pseudocode

```c

```

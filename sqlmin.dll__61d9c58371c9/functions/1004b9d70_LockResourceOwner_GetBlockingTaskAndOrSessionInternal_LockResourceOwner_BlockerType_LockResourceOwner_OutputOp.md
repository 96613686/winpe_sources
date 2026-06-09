# LockResourceOwner::GetBlockingTaskAndOrSessionInternal(LockResourceOwner::BlockerType,LockResourceOwner::OutputOptions,SOS_Task * &,short &,long &,FederatedXactId *)

- ea: `0x1004b9d70`
- end: `0x1004ba100`
- name: `?GetBlockingTaskAndOrSessionInternal@LockResourceOwner@@AEAA?AW4BlockerStatus@IResourceOwner@@W4BlockerType@1@W4OutputOptions@1@AEAPEAVSOS_Task@@AEAFAEAJPEAVFederatedXactId@@@Z`
- size: `912`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `service_task`

## callers

- `0x1004b9b50`
- `0x101760a60`

## callees

- `0x1004060e0`
- `0x100406110`
- `0x1004162a0`
- `0x10041f670`
- `0x10047b3f0`
- `0x1004b9d70`
- `0x1004c37b0`
- `0x1004c39d0`
- `0x1005486c0`
- `0x1005d8b90`
- `0x1006c5e70`
- `0x1006c6280`
- `0x1006c6560`
- `0x101760f70`
- `0x1018818e0`
- `0x1023aecb0`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x101758a2d`
- `KERNEL32!VirtualFree` at `0x101758a2d`
- `KERNEL32!VirtualProtect` at `0x101758898`
- `KERNEL32!VirtualProtect` at `0x101758898`
- `KERNEL32!QueryPerformanceCounter` at `0x101757f43`
- `KERNEL32!QueryPerformanceCounter` at `0x101757f6f`
- `KERNEL32!QueryPerformanceCounter` at `0x1017580dc`
- `KERNEL32!QueryPerformanceCounter` at `0x101758106`
- `KERNEL32!QueryPerformanceCounter` at `0x1017584b6`
- `KERNEL32!QueryPerformanceCounter` at `0x1017584e4`
- `KERNEL32!QueryPerformanceCounter` at `0x1017585cd`
- `KERNEL32!QueryPerformanceCounter` at `0x10175861a`
- `KERNEL32!QueryPerformanceCounter` at `0x1017587c5`
- `KERNEL32!QueryPerformanceCounter` at `0x101758811`
- `KERNEL32!QueryPerformanceCounter` at `0x101758b62`
- `KERNEL32!QueryPerformanceCounter` at `0x101758b90`
- `KERNEL32!QueryPerformanceCounter` at `0x101758d9e`
- `KERNEL32!QueryPerformanceCounter` at `0x101758dc8`
- `KERNEL32!QueryPerformanceCounter` at `0x101757f43`
- `KERNEL32!QueryPerformanceCounter` at `0x101757f6f`
- `KERNEL32!QueryPerformanceCounter` at `0x1017580dc`
- `KERNEL32!QueryPerformanceCounter` at `0x101758106`
- `KERNEL32!QueryPerformanceCounter` at `0x1017584b6`
- `KERNEL32!QueryPerformanceCounter` at `0x1017584e4`
- `KERNEL32!QueryPerformanceCounter` at `0x1017585cd`
- `KERNEL32!QueryPerformanceCounter` at `0x10175861a`
- `KERNEL32!QueryPerformanceCounter` at `0x1017587c5`
- `KERNEL32!QueryPerformanceCounter` at `0x101758811`
- `KERNEL32!QueryPerformanceCounter` at `0x101758b62`
- `KERNEL32!QueryPerformanceCounter` at `0x101758b90`
- `KERNEL32!QueryPerformanceCounter` at `0x101758d9e`
- `KERNEL32!QueryPerformanceCounter` at `0x101758dc8`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004b9faf`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004ba0b3`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101757fcd`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101758387`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x10175892a`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1017589c9`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101758c1c`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101758eb8`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101758f13`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101757ed9`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10175807a`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10175844f`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10175856f`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101758766`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101758afb`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101758d38`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x101758a16`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1017585da`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1017587d2`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101757f2f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101757f5b`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1017580cc`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1017580f6`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1017584a2`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1017584d0`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1017585ba`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101758606`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1017587b1`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1017587fd`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101758b4e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101758b7c`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101758d8e`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101758db8`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x10175870a`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x10175870a`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1004ba08e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10175821b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10175836b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x1004ba08e`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10175821b`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x10175836b`
- `sqldk!SystemThread_TlsIndex` at `0x101757efd`
- `sqldk!SystemThread_TlsIndex` at `0x10175809e`
- `sqldk!SystemThread_TlsIndex` at `0x101758470`
- `sqldk!SystemThread_TlsIndex` at `0x10175858c`
- `sqldk!SystemThread_TlsIndex` at `0x10175866d`
- `sqldk!SystemThread_TlsIndex` at `0x101758783`
- `sqldk!SystemThread_TlsIndex` at `0x101758b1c`
- `sqldk!SystemThread_TlsIndex` at `0x101758d5c`
- `sqldk!SystemThread_TlsOffset` at `0x101757f06`
- `sqldk!SystemThread_TlsOffset` at `0x1017580a7`
- `sqldk!SystemThread_TlsOffset` at `0x101758479`
- `sqldk!SystemThread_TlsOffset` at `0x101758595`
- `sqldk!SystemThread_TlsOffset` at `0x101758676`
- `sqldk!SystemThread_TlsOffset` at `0x10175878c`
- `sqldk!SystemThread_TlsOffset` at `0x101758b25`
- `sqldk!SystemThread_TlsOffset` at `0x101758d65`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101757fd9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10175815b`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101758393`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101758936`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1017589d5`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101758c28`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101758cb5`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101758ec4`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101758f1f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101757fd9`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10175815b`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101758393`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101758936`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1017589d5`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101758c28`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101758cb5`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101758ec4`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101758f1f`

## pseudocode

```c

```

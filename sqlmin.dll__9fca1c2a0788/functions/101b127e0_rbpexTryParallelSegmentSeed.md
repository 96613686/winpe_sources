# rbpexTryParallelSegmentSeed

- ea: `0x101b127e0`
- end: `0x101b13c06`
- name: `rbpexTryParallelSegmentSeed`
- size: `5158`
- prototype: `__int64 __usercall@<rax>(RBPEXImpl *this@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `service_task`

## callers

- `0x101b14530`

## callees

- `0x100401490`
- `0x100401fcf`
- `0x1004162a0`
- `0x10042d820`
- `0x10042d8d4`
- `0x10043e000`
- `0x10045e1b8`
- `0x10047b3f0`
- `0x1004c37b0`
- `0x1004c39d0`
- `0x1005486c0`
- `0x1005aebe0`
- `0x1005d8b90`
- `0x1006aace0`
- `0x1006c5e70`
- `0x1006c6280`
- `0x1006c6560`
- `0x101acb420`
- `0x101b0bb70`
- `0x101b0bc00`
- `0x101b0bda0`
- `0x101b127e0`
- `0x101b14fe0`
- `0x102387bc0`
- `0x1023ae3e0`
- `0x1023ae6b0`
- `0x1023aecb0`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x101b138f1`
- `KERNEL32!VirtualFree` at `0x101b138f1`
- `KERNEL32!VirtualProtect` at `0x101b1379e`
- `KERNEL32!VirtualProtect` at `0x101b1379e`
- `KERNEL32!QueryPerformanceCounter` at `0x101b128f4`
- `KERNEL32!QueryPerformanceCounter` at `0x101b12fb5`
- `KERNEL32!QueryPerformanceCounter` at `0x101b134f6`
- `KERNEL32!QueryPerformanceCounter` at `0x101b13548`
- `KERNEL32!QueryPerformanceCounter` at `0x101b136bc`
- `KERNEL32!QueryPerformanceCounter` at `0x101b13714`
- `KERNEL32!QueryPerformanceCounter` at `0x101b128f4`
- `KERNEL32!QueryPerformanceCounter` at `0x101b12fb5`
- `KERNEL32!QueryPerformanceCounter` at `0x101b134f6`
- `KERNEL32!QueryPerformanceCounter` at `0x101b13548`
- `KERNEL32!QueryPerformanceCounter` at `0x101b136bc`
- `KERNEL32!QueryPerformanceCounter` at `0x101b13714`
- `KERNEL32!GetCurrentThreadId` at `0x101b139d8`
- `KERNEL32!GetCurrentThreadId` at `0x101b13b41`
- `KERNEL32!GetCurrentThreadId` at `0x101b139d8`
- `KERNEL32!GetCurrentThreadId` at `0x101b13b41`
- `sqldk!?WaitForDone@SOS_Task@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z` at `0x101b133a8`
- `sqldk!?WaitForDone@SOS_Task@@QEAA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z` at `0x101b133a8`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101b13854`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x101b13892`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101b1349c`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x101b1365e`
- `sqldk!?SOS_Tracing_osTrace@@3KA` at `0x101b138da`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101b1350a`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x101b136d3`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101b128e4`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101b12f9f`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101b134e7`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101b13538`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101b136a9`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101b13701`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x101b13a29`
- `sqldk!?sm_QueryPerformanceFrequency@Base_PublicGlobals@@2T_LARGE_INTEGER@@A` at `0x101b13a35`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x101b13169`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x101b13343`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x101b13169`
- `sqldk!?EnqueueTask@SOS_OS@@SA?AW4SOS_RESULT@@P6APEAXPEAX@Z0KPEAPEAVSOS_Task@@_K@Z` at `0x101b13343`
- `sqldk!?SetAbort@SOS_Task@@QEAAXW4TASK_ABORT_TYPE@1@@Z` at `0x101b13275`
- `sqldk!?SetAbort@SOS_Task@@QEAAXW4TASK_ABORT_TYPE@1@@Z` at `0x101b13275`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x101b13602`
- `sqldk!?IsTaskStoreDisabled@SOS_Node@@QEAA_NXZ` at `0x101b13602`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b12959`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b12dfa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b12e25`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b12e96`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b133d7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b13976`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b12959`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b12dfa`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b12e25`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b12e96`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b133d7`
- `sqldk!?utassert_fail@@YAXIPEBD0H0ZZ` at `0x101b13976`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101b12c26`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101b12ce0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101b1303f`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101b12c26`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101b12ce0`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x101b1303f`
- `sqldk!SystemThread_TlsIndex` at `0x101b12884`
- `sqldk!SystemThread_TlsIndex` at `0x101b131be`
- `sqldk!SystemThread_TlsIndex` at `0x101b134b9`
- `sqldk!SystemThread_TlsIndex` at `0x101b135a2`
- `sqldk!SystemThread_TlsIndex` at `0x101b1367b`
- `sqldk!SystemThread_TlsOffset` at `0x101b1288d`
- `sqldk!SystemThread_TlsOffset` at `0x101b131c7`
- `sqldk!SystemThread_TlsOffset` at `0x101b134c2`
- `sqldk!SystemThread_TlsOffset` at `0x101b135ab`
- `sqldk!SystemThread_TlsOffset` at `0x101b13684`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101b128a8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101b131e6`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101b128a8`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x101b131e6`
- `sqldk!??_V@YAXPEAX@Z` at `0x101b12c8a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101b12f73`
- `sqldk!??_V@YAXPEAX@Z` at `0x101b13054`
- `sqldk!??_V@YAXPEAX@Z` at `0x101b13bc9`
- `sqldk!??_V@YAXPEAX@Z` at `0x101b13bd4`
- `sqldk!??_V@YAXPEAX@Z` at `0x101b12c8a`
- `sqldk!??_V@YAXPEAX@Z` at `0x101b12f73`
- `sqldk!??_V@YAXPEAX@Z` at `0x101b13054`
- `sqldk!??_V@YAXPEAX@Z` at `0x101b13bc9`
- `sqldk!??_V@YAXPEAX@Z` at `0x101b13bd4`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101b13860`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101b1389e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101b13860`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x101b1389e`
- `rbio!RbIoConnectionClose` at `0x101b12af7`
- `rbio!RbIoConnectionClose` at `0x101b12af7`
- `rbio!RbIoConnectionRelease` at `0x101b12aff`
- `rbio!RbIoConnectionRelease` at `0x101b12aff`
- `rbio!RbIoGetRbpexSeedStatus` at `0x101b129cd`
- `rbio!RbIoGetRbpexSeedStatus` at `0x101b129cd`
- `striped!StripedFcbGetPageRange` at `0x101b12b42`
- `striped!StripedFcbGetPageRange` at `0x101b12b42`
- `striped!StripedHandleGetCellMd` at `0x101b12ba7`
- `striped!StripedHandleGetCellMd` at `0x101b12ba7`
- `striped!IsStripedPathPrefix` at `0x101b12b80`
- `striped!IsStripedPathPrefix` at `0x101b12b80`
- `hkengine!HkTransactionAbort` at `0x101b13b89`
- `hkengine!HkTransactionAbort` at `0x101b13b89`
- `hkengine!HkTransactionAlloc` at `0x101b12f0c`
- `hkengine!HkTransactionAlloc` at `0x101b12f0c`

## string_xrefs

- `0x101b13986`: `%ls - all %u threads exited`
- `0x101b13295`: `%ls: aborting seedTasks[%u] due hr: 0x%08x - threadCount: %u, UsePeer: %d`
- `0x101b1338d`: `%ls: waiting for seedTasks[%u] - threadCount: %u, UsePeer: %d`

## pseudocode

```c

```

# Spinlock<25,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x100402570`
- end: `0x100402819`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAX_K@Z`
- size: `681`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x100401b20`
- `0x100401e80`
- `0x100402080`
- `0x100402a10`
- `0x10040d680`
- `0x10041d520`

## callees

- `0x100402570`

## import_xrefs

- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100402636`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x1004026f0`
- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x1004026f9`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x10040270d`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004026a9`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004026a9`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004026bd`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004026bd`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x1004027d3`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x1004027d3`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040262b`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040262b`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100402616`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100402616`
- `sqldk!SystemThread_TlsIndex` at `0x1004025a7`
- `sqldk!SystemThread_TlsOffset` at `0x1004025b1`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004025ef`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040271e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040271e`

## pseudocode

```c

```

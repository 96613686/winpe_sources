# Spinlock<475,19,258>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x10047f890`
- end: `0x10047fb39`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BNL@$0BD@$0BAC@@@AEAAX_K@Z`
- size: `681`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x10047f0e0`
- `0x10047f320`

## callees

- `0x10047f890`

## import_xrefs

- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10047f956`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10047fa10`
- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10047fa19`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x10047fa2d`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10047f9c9`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10047f9c9`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10047f9dd`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10047f9dd`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10047faf3`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10047faf3`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10047f94b`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10047f94b`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10047f936`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10047f936`
- `sqldk!SystemThread_TlsIndex` at `0x10047f8c7`
- `sqldk!SystemThread_TlsOffset` at `0x10047f8d1`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10047f90f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047fa3e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10047fa3e`

## pseudocode

```c

```

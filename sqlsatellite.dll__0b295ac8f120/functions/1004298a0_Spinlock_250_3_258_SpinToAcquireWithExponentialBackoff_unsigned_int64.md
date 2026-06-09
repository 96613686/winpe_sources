# Spinlock<250,3,258>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x1004298a0`
- end: `0x100429b49`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0PK@$02$0BAC@@@AEAAX_K@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100423750`

## callees

- `0x1004298a0`

## import_xrefs

- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100429966`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100429a20`
- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x100429a29`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x100429a3d`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004299d9`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004299d9`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004299ed`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004299ed`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x100429b03`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x100429b03`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10042995b`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10042995b`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100429946`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100429946`
- `sqldk!SystemThread_TlsIndex` at `0x1004298d7`
- `sqldk!SystemThread_TlsOffset` at `0x1004298e1`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10042991f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100429a4e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100429a4e`

## pseudocode

```c

```

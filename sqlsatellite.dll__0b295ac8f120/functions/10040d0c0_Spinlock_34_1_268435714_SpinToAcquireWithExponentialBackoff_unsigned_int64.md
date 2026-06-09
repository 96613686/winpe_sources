# Spinlock<34,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x10040d0c0`
- end: `0x10040d369`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAX_K@Z`
- size: `681`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x100409790`
- `0x10040af40`
- `0x10040c0e0`
- `0x10041de00`
- `0x10041e0a0`
- `0x100446b10`
- `0x1004704c0`
- `0x100477b20`

## callees

- `0x10040d0c0`

## import_xrefs

- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10040d186`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10040d240`
- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10040d249`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x10040d25d`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10040d1f9`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10040d1f9`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10040d20d`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10040d20d`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040d323`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040d323`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040d17b`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040d17b`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040d166`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040d166`
- `sqldk!SystemThread_TlsIndex` at `0x10040d0f7`
- `sqldk!SystemThread_TlsOffset` at `0x10040d101`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040d13f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040d26e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040d26e`

## pseudocode

```c

```

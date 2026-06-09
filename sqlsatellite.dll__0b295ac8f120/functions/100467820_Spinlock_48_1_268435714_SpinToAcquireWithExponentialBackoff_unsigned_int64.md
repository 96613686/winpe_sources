# Spinlock<48,1,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x100467820`
- end: `0x100467ac9`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0DA@$00$0BAAAABAC@@@AEAAX_K@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100466b20`

## callees

- `0x100467820`

## import_xrefs

- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x1004678e6`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x1004679a0`
- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x1004679a9`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x1004679bd`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100467959`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x100467959`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10046796d`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10046796d`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x100467a83`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x100467a83`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004678db`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004678db`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004678c6`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004678c6`
- `sqldk!SystemThread_TlsIndex` at `0x100467857`
- `sqldk!SystemThread_TlsOffset` at `0x100467861`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10046789f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004679ce`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004679ce`

## pseudocode

```c

```

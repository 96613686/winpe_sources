# Spinlock<22,1,268435713>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x100477870`
- end: `0x100477b19`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0BG@$00$0BAAAABAB@@@AEAAX_K@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100476df0`

## callees

- `0x100477870`

## import_xrefs

- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x100477936`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x1004779f0`
- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x1004779f9`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x100477a0d`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004779a9`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004779a9`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004779bd`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x1004779bd`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x100477ad3`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x100477ad3`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10047792b`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10047792b`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100477916`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100477916`
- `sqldk!SystemThread_TlsIndex` at `0x1004778a7`
- `sqldk!SystemThread_TlsOffset` at `0x1004778b1`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004778ef`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100477a1e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100477a1e`

## pseudocode

```c

```

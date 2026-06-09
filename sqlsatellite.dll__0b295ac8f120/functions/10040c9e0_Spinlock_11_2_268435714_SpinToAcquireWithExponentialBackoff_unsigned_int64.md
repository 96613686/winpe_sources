# Spinlock<11,2,268435714>::SpinToAcquireWithExponentialBackoff(unsigned __int64)

- ea: `0x10040c9e0`
- end: `0x10040cc89`
- name: `?SpinToAcquireWithExponentialBackoff@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAX_K@Z`
- size: `681`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x100409790`
- `0x10040af40`
- `0x10040c0e0`
- `0x100446b10`
- `0x100464c60`
- `0x100464e90`
- `0x1004704c0`
- `0x100477b20`

## callees

- `0x10040c9e0`

## import_xrefs

- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10040caa6`
- `sqldk!?sm_cpuCount@SOS_PublicGlobals@@2KA` at `0x10040cb60`
- `sqldk!?sm_StaggerEnabledForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10040cb69`
- `sqldk!?sm_SpinIncrement@SOS_PublicGlobals@@2_KA` at `0x10040cb7d`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10040cb19`
- `sqldk!?GetSpins@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10040cb19`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10040cb2d`
- `sqldk!?GetCollisions@SpinlockStat@@QEBA_KGW4SPINLOCK_CATEGORY@@@Z` at `0x10040cb2d`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040cc43`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040cc43`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040ca9b`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040ca9b`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040ca86`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040ca86`
- `sqldk!SystemThread_TlsIndex` at `0x10040ca17`
- `sqldk!SystemThread_TlsOffset` at `0x10040ca21`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040ca5f`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040cb8e`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x10040cb8e`

## pseudocode

```c

```

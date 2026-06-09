# Spinlock<48,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)

- ea: `0x1004675e0`
- end: `0x100467810`
- name: `?SpinToAcquireOptimistic@?$Spinlock@$0DA@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100466b20`

## callees

- `0x1004675e0`

## import_xrefs

- `sqldk!?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x1004675fc`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x1004677df`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x1004677df`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004676b3`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x1004676b3`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10046769e`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10046769e`
- `sqldk!SystemThread_TlsIndex` at `0x100467637`
- `sqldk!SystemThread_TlsOffset` at `0x100467641`
- `sqldk!?sm_SpinCounter@SOS_PublicGlobals@@2_JA` at `0x100467706`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10046767b`

## pseudocode

```c

```

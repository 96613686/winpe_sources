# Spinlock<475,19,258>::SpinToAcquireOptimistic(Worker *,unsigned __int64)

- ea: `0x10047f670`
- end: `0x10047f88a`
- name: `?SpinToAcquireOptimistic@?$Spinlock@$0BNL@$0BD@$0BAC@@@AEAAXPEAVWorker@@_K@Z`
- size: `538`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x10047f0e0`
- `0x10047f320`

## callees

- `0x10047f670`

## import_xrefs

- `sqldk!?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10047f686`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10047f85e`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10047f85e`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10047f73a`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10047f73a`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10047f725`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10047f725`
- `sqldk!SystemThread_TlsIndex` at `0x10047f6be`
- `sqldk!SystemThread_TlsOffset` at `0x10047f6c8`
- `sqldk!?sm_SpinCounter@SOS_PublicGlobals@@2_JA` at `0x10047f78d`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10047f702`

## pseudocode

```c

```

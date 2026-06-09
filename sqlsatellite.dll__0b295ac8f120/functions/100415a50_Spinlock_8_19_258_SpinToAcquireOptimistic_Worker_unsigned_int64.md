# Spinlock<8,19,258>::SpinToAcquireOptimistic(Worker *,unsigned __int64)

- ea: `0x100415a50`
- end: `0x100415c6a`
- name: `?SpinToAcquireOptimistic@?$Spinlock@$07$0BD@$0BAC@@@AEAAXPEAVWorker@@_K@Z`
- size: `538`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x100412320`
- `0x100413220`
- `0x1004700c0`
- `0x100470280`
- `0x100471430`
- `0x100471880`
- `0x100472d40`
- `0x100472f00`
- `0x100474660`
- `0x100475fd0`

## callees

- `0x100415a50`

## import_xrefs

- `sqldk!?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x100415a66`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x100415c3e`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x100415c3e`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100415b1a`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100415b1a`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100415b05`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100415b05`
- `sqldk!SystemThread_TlsIndex` at `0x100415a9e`
- `sqldk!SystemThread_TlsOffset` at `0x100415aa8`
- `sqldk!?sm_SpinCounter@SOS_PublicGlobals@@2_JA` at `0x100415b6d`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100415ae2`

## pseudocode

```c

```

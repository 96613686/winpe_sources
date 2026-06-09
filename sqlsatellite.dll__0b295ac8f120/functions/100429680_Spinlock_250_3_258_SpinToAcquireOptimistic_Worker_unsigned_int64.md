# Spinlock<250,3,258>::SpinToAcquireOptimistic(Worker *,unsigned __int64)

- ea: `0x100429680`
- end: `0x10042989a`
- name: `?SpinToAcquireOptimistic@?$Spinlock@$0PK@$02$0BAC@@@AEAAXPEAVWorker@@_K@Z`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x100423750`

## callees

- `0x100429680`

## import_xrefs

- `sqldk!?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x100429696`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10042986e`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10042986e`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10042974a`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10042974a`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100429735`
- `sqldk!?GetClientProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x100429735`
- `sqldk!SystemThread_TlsIndex` at `0x1004296ce`
- `sqldk!SystemThread_TlsOffset` at `0x1004296d8`
- `sqldk!?sm_SpinCounter@SOS_PublicGlobals@@2_JA` at `0x10042979d`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100429712`

## pseudocode

```c

```

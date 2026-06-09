# Spinlock<34,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)

- ea: `0x10040ce80`
- end: `0x10040d0b0`
- name: `?SpinToAcquireOptimistic@?$Spinlock@$0CC@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z`
- size: `560`
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

- `0x10040ce80`

## import_xrefs

- `sqldk!?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10040ce9c`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040d07f`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040d07f`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040cf53`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040cf53`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040cf3e`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040cf3e`
- `sqldk!SystemThread_TlsIndex` at `0x10040ced7`
- `sqldk!SystemThread_TlsOffset` at `0x10040cee1`
- `sqldk!?sm_SpinCounter@SOS_PublicGlobals@@2_JA` at `0x10040cfa6`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040cf1b`

## pseudocode

```c

```

# Spinlock<25,1,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)

- ea: `0x100402330`
- end: `0x100402560`
- name: `?SpinToAcquireOptimistic@?$Spinlock@$0BJ@$00$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z`
- size: `560`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x100401b20`
- `0x100401e80`
- `0x100402080`
- `0x100402a10`
- `0x10040d680`
- `0x10041d520`

## callees

- `0x100402330`

## import_xrefs

- `sqldk!?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10040234c`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040252f`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040252f`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100402403`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x100402403`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004023ee`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x1004023ee`
- `sqldk!SystemThread_TlsIndex` at `0x100402387`
- `sqldk!SystemThread_TlsOffset` at `0x100402391`
- `sqldk!?sm_SpinCounter@SOS_PublicGlobals@@2_JA` at `0x100402456`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x1004023cb`

## pseudocode

```c

```

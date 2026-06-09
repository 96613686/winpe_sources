# Spinlock<11,2,268435714>::SpinToAcquireOptimistic(Worker *,unsigned __int64)

- ea: `0x10040c7a0`
- end: `0x10040c9d0`
- name: `?SpinToAcquireOptimistic@?$Spinlock@$0L@$01$0BAAAABAC@@@AEAAXPEAVWorker@@_K@Z`
- size: `560`
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

- `0x10040c7a0`

## import_xrefs

- `sqldk!?sm_ShouldResetSpinsForSpinToAcquire@SOS_PublicGlobals@@2_NA` at `0x10040c7bc`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040c99f`
- `sqldk!?Backoff@SpinlockBase@@IEAAXAEAVSpinInfo@1@@Z` at `0x10040c99f`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040c873`
- `sqldk!?GetSpinlockStats@PerProcessGlobals@@QEAAPEAVSpinlockStat@@G@Z` at `0x10040c873`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040c85e`
- `sqldk!?GetSOSProcessGlobals@SOS_OS@@SAPEAVPerProcessGlobals@@XZ` at `0x10040c85e`
- `sqldk!SystemThread_TlsIndex` at `0x10040c7f7`
- `sqldk!SystemThread_TlsOffset` at `0x10040c801`
- `sqldk!?sm_SpinCounter@SOS_PublicGlobals@@2_JA` at `0x10040c8c6`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040c83b`

## pseudocode

```c

```

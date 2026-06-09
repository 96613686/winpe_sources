# EventAutoInternal<SuspendQueueSLock>::Signal(SOS_EVENT_SIGNAL_OPTIONS)

- ea: `0x100402a10`
- end: `0x100402c5c`
- name: `?Signal@?$EventAutoInternal@USuspendQueueSLock@@@@UEAAXW4SOS_EVENT_SIGNAL_OPTIONS@@@Z`
- size: `588`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1004557f0`

## callees

- `0x100402330`
- `0x100402570`
- `0x100402820`
- `0x100402a10`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100402b05`
- `KERNEL32!QueryPerformanceCounter` at `0x100402b56`
- `KERNEL32!QueryPerformanceCounter` at `0x100402b05`
- `KERNEL32!QueryPerformanceCounter` at `0x100402b56`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x100402bc5`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100402af6`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x100402b46`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x100402b19`
- `sqldk!?SignalAndGetAll@WorkerWaitQueue@@QEAAHPEAV?$SEList@VWorkerWaitElem@@$0A@@@0H@Z` at `0x100402b97`
- `sqldk!?SignalAndGetAll@WorkerWaitQueue@@QEAAHPEAV?$SEList@VWorkerWaitElem@@$0A@@@0H@Z` at `0x100402b97`
- `sqldk!?ResumeBulk@SOS_Scheduler@@SAXPEAV?$SEList@VWorkerWaitElem@@$0A@@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z` at `0x100402c3e`
- `sqldk!?ResumeBulk@SOS_Scheduler@@SAXPEAV?$SEList@VWorkerWaitElem@@$0A@@@W4SOS_QUEUE_PLACE@@W4SOS_RESULT@@@Z` at `0x100402c3e`
- `sqldk!SystemThread_TlsIndex` at `0x100402ac8`
- `sqldk!SystemThread_TlsOffset` at `0x100402ad1`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x100402aa8`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100402bd1`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x100402bd1`

## pseudocode

```c

```

# EventInternal<SuspendQueueSLock>::ExecutePreWaitSteps(Worker *,ulong,SOS_SYNC_WAIT_OPTIONS)

- ea: `0x100402080`
- end: `0x100402314`
- name: `?ExecutePreWaitSteps@?$EventInternal@USuspendQueueSLock@@@@UEAA?AW4SOS_RESULT@@PEAVWorker@@KW4SOS_SYNC_WAIT_OPTIONS@@@Z`
- size: `660`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x100402080`
- `0x100402330`
- `0x100402570`
- `0x100402820`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1004021ae`
- `KERNEL32!QueryPerformanceCounter` at `0x100402207`
- `KERNEL32!QueryPerformanceCounter` at `0x1004021ae`
- `KERNEL32!QueryPerformanceCounter` at `0x100402207`
- `sqldk!?sm_SpinlockStatSnapshot@SOS_PublicGlobals@@2_NA` at `0x1004022af`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x10040219a`
- `sqldk!?sm_invariantTscAvailable@Base_PublicGlobals@@2HA` at `0x1004021f3`
- `sqldk!?sm_traceFlags@SOS_PublicGlobals@@2PAEA` at `0x1004021c6`
- `sqldk!?OSYieldNoAbort@Worker@@QEAAXXZ` at `0x10040210b`
- `sqldk!?OSYieldNoAbort@Worker@@QEAAXXZ` at `0x10040210b`
- `sqldk!?TrySignal@WorkerWaitContext@@QEAA?AW4WorkerSignalResult@@PEAVMinWaitableBase@@W4WorkerSignalType@@@Z` at `0x100402266`
- `sqldk!?TrySignal@WorkerWaitContext@@QEAA?AW4WorkerSignalResult@@PEAVMinWaitableBase@@W4WorkerSignalType@@@Z` at `0x100402266`
- `sqldk!?EnqueueWait@WorkerWaitContext@@QEAAXPEAVMinWaitableBase@@W4SOS_QUEUE_PLACE@@@Z` at `0x100402298`
- `sqldk!?EnqueueWait@WorkerWaitContext@@QEAAXPEAVMinWaitableBase@@W4SOS_QUEUE_PLACE@@@Z` at `0x100402298`
- `sqldk!SystemThread_TlsIndex` at `0x10040216c`
- `sqldk!SystemThread_TlsOffset` at `0x100402175`
- `sqldk!?sm_osStats@SOS_PublicGlobals@@2KA` at `0x10040214c`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004022bb`
- `api-ms-win-crt-utility-l1-1-0!rand` at `0x1004022bb`

## pseudocode

```c

```

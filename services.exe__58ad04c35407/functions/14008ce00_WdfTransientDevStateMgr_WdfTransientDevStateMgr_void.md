# WdfTransientDevStateMgr::~WdfTransientDevStateMgr(void)

- ea: `0x14008ce00`
- end: `0x14008cec2`
- name: `??1WdfTransientDevStateMgr@@QEAA@XZ`
- size: `194`
- prototype: `void __fastcall(WdfTransientDevStateMgr *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140089508`

## callees

- `0x140004c58`
- `0x14001b928`
- `0x14008ce00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x14008ce9c`
- `api-ms-win-core-synch-l1-1-0!CancelWaitableTimer` at `0x14008ce9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ce21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14008ce21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008cea6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008cea6`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14008ceb6`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14008ceb6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x14008ce17`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x14008ce17`

## string_xrefs

- `0x14008ce5e`: `Unable to get threadpool to stop waiting on timer. Callbacks may still be running or about to run.`

## pseudocode

```c

```

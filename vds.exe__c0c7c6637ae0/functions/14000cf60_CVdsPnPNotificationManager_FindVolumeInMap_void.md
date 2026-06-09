# CVdsPnPNotificationManager::FindVolumeInMap(void *)

- ea: `0x14000cf60`
- end: `0x14000d0e9`
- name: `?FindVolumeInMap@CVdsPnPNotificationManager@@AEAAPEAGPEAX@Z`
- size: `393`
- prototype: `unsigned __int16 *__fastcall(CVdsPnPNotificationManager *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000cd7c`
- `0x14000fd1c`

## callees

- `0x14000cf60`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000d0b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000d0b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000cfcc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000cfcc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d00a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d00a`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x14000cfe2`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x14000cfe2`
- `vdsutil!VdsHeapAlloc` at `0x14000d01b`
- `vdsutil!VdsHeapAlloc` at `0x14000d01b`
- `vdsutil!VdsTraceEx` at `0x14000d08e`
- `vdsutil!VdsTraceEx` at `0x14000d0a5`
- `vdsutil!VdsTraceEx` at `0x14000d08e`
- `vdsutil!VdsTraceEx` at `0x14000d0a5`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000cf9c`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000cf9c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000d0bc`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000d0bc`

## string_xrefs

- `0x14000d07f`: `CVdsPnPNotificationManager::FindVolumeInMap: not enoughmemory to make a copy of device path. Notificationmay be lost.`

## pseudocode

```c

```

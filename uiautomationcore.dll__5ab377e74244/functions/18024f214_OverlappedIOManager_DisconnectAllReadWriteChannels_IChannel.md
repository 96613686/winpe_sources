# OverlappedIOManager::DisconnectAllReadWriteChannels(IChannel *)

- ea: `0x18024f214`
- end: `0x18024f318`
- name: `?DisconnectAllReadWriteChannels@OverlappedIOManager@@QEAAXPEAUIChannel@@@Z`
- size: `260`
- prototype: `void __fastcall(OverlappedIOManager *__hidden this, struct ChannelInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1801f7930`

## callees

- `0x18024f1b8`
- `0x18024f214`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18024f288`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18024f288`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18024f233`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18024f262`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18024f2c7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18024f233`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18024f262`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18024f2c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18024f2ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18024f309`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18024f2ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18024f309`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18024f24d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18024f24d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024f2d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024f2d4`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18024f2b1`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18024f2b1`

## pseudocode

```c

```

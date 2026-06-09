# VidNotificationDispatcher::TranslateIoPort(uint,ushort,EMU_IO_PORT_HANDLER_FLAGS,int,IIoPortHandlerContext * *)

- ea: `0x1400432b0`
- end: `0x1400435ba`
- name: `?TranslateIoPort@VidNotificationDispatcher@@UEAAJIGW4EMU_IO_PORT_HANDLER_FLAGS@@HPEAPEAUIIoPortHandlerContext@@@Z`
- size: `778`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140043164`
- `0x14027aab0`

## callees

- `0x1400432b0`
- `0x14009d7cc`
- `0x140132960`
- `0x1401ebf90`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004334b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14004334b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14004331d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14004331d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043482`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043482`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400434b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400434b5`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1400434e9`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1400434e9`
- `vid!VidCheckForIoIntercept` at `0x14004356e`
- `vid!VidCheckForIoIntercept` at `0x14004356e`

## string_xrefs

- `0x140043521`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```

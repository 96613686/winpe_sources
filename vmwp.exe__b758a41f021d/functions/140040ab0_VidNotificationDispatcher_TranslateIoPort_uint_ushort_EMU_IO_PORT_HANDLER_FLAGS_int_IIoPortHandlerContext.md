# VidNotificationDispatcher::TranslateIoPort(uint,ushort,EMU_IO_PORT_HANDLER_FLAGS,int,IIoPortHandlerContext * *)

- ea: `0x140040ab0`
- end: `0x140040dba`
- name: `?TranslateIoPort@VidNotificationDispatcher@@UEAAJIGW4EMU_IO_PORT_HANDLER_FLAGS@@HPEAPEAUIIoPortHandlerContext@@@Z`
- size: `778`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140040964`
- `0x140280dc0`

## callees

- `0x140040ab0`
- `0x1400ba144`
- `0x14011ea40`
- `0x1401dbb30`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140040b1d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140040b1d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140040b4b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140040b4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040c82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040c82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140040cb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140040cb5`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140040ce9`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140040ce9`
- `vid!VidCheckForIoIntercept` at `0x140040d6e`
- `vid!VidCheckForIoIntercept` at `0x140040d6e`

## string_xrefs

- `0x140040d21`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```

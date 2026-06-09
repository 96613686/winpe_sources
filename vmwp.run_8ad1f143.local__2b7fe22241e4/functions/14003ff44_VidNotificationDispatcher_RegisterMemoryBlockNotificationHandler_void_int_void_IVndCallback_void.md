# VidNotificationDispatcher::RegisterMemoryBlockNotificationHandler(void *,int,void *,IVndCallback &,void * &)

- ea: `0x14003ff44`
- end: `0x140040232`
- name: `?RegisterMemoryBlockNotificationHandler@VidNotificationDispatcher@@QEAAJPEAXH0AEAUIVndCallback@@AEAPEAX@Z`
- size: `750`
- prototype: `__int64 __fastcall(VidNotificationDispatcher *__hidden this, void *, int, void *, struct IVndCallback *, void **)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14003f490`

## callees

- `0x140021d20`
- `0x14002439c`
- `0x14003ff44`
- `0x140040ff8`
- `0x140041a5c`
- `0x140042260`
- `0x14005497c`
- `0x140078cb8`
- `0x140096760`
- `0x14009d7cc`
- `0x140132d50`
- `0x14013361c`
- `0x14027b3a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003ffa8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14003ffa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004004c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004004c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003ff6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14003ff6d`
- `vid!VidSetMemoryBlockNotificationQueue` at `0x14003ffd5`
- `vid!VidSetMemoryBlockNotificationQueue` at `0x14003ffd5`

## string_xrefs

- `0x140040220`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```

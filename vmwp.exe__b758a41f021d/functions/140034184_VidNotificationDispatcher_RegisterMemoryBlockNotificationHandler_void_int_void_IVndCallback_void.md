# VidNotificationDispatcher::RegisterMemoryBlockNotificationHandler(void *,int,void *,IVndCallback &,void * &)

- ea: `0x140034184`
- end: `0x140034472`
- name: `?RegisterMemoryBlockNotificationHandler@VidNotificationDispatcher@@QEAAJPEAXH0AEAUIVndCallback@@AEAPEAX@Z`
- size: `750`
- prototype: `__int64 __fastcall(VidNotificationDispatcher *__hidden this, void *, int, void *, struct IVndCallback *, void **)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400336d0`

## callees

- `0x140022290`
- `0x14002490c`
- `0x140034184`
- `0x140035238`
- `0x140035c9c`
- `0x1400364a0`
- `0x1400544a8`
- `0x1400812e4`
- `0x14008a328`
- `0x1400ba144`
- `0x14011ee30`
- `0x14011f6fc`
- `0x1402816b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400341e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400341e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003428c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140034256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003428c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400341ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400341ad`
- `vid!VidSetMemoryBlockNotificationQueue` at `0x140034215`
- `vid!VidSetMemoryBlockNotificationQueue` at `0x140034215`

## string_xrefs

- `0x140034460`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```

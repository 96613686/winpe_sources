# VidNotificationDispatcher::RegisterApicEoiHandler(uint,void *,IVndCallback &,void * &)

- ea: `0x140281a40`
- end: `0x140281c0d`
- name: `?RegisterApicEoiHandler@VidNotificationDispatcher@@QEAAJIPEAXAEAUIVndCallback@@AEAPEAX@Z`
- size: `461`
- prototype: `__int64 __usercall@<rax>(VidNotificationDispatcher *__hidden this@<rcx>, unsigned int@<edx>, void *@<r8>, struct IVndCallback *@<r9>, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14027f6a0`

## callees

- `0x140035238`
- `0x140035c9c`
- `0x1400364a0`
- `0x1400544a8`
- `0x14008a328`
- `0x1400ba144`
- `0x1400cb87c`
- `0x1402816b0`
- `0x140281a40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140281adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140281b70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140281adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140281b70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140281a69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140281a69`
- `vid!VidRegisterApicEoiHandler` at `0x140281b60`
- `vid!VidRegisterApicEoiHandler` at `0x140281b60`

## string_xrefs

- `0x140281bfb`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```

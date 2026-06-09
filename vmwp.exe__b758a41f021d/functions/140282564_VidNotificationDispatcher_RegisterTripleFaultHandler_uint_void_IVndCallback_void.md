# VidNotificationDispatcher::RegisterTripleFaultHandler(uint,void *,IVndCallback &,void * &)

- ea: `0x140282564`
- end: `0x140282731`
- name: `?RegisterTripleFaultHandler@VidNotificationDispatcher@@QEAAJIPEAXAEAUIVndCallback@@AEAPEAX@Z`
- size: `461`
- prototype: `__int64 __usercall@<rax>(VidNotificationDispatcher *__hidden this@<rcx>, unsigned int@<edx>, void *@<r8>, struct IVndCallback *@<r9>, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14027f7a0`

## callees

- `0x140035238`
- `0x140035c9c`
- `0x1400364a0`
- `0x1400544a8`
- `0x14008a328`
- `0x1400ba144`
- `0x1400cb87c`
- `0x1402816b0`
- `0x140282564`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140282600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140282694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140282600`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140282694`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028258d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14028258d`
- `vid!VidRegisterTripleFaultHandler` at `0x140282684`
- `vid!VidRegisterTripleFaultHandler` at `0x140282684`

## string_xrefs

- `0x14028271f`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```

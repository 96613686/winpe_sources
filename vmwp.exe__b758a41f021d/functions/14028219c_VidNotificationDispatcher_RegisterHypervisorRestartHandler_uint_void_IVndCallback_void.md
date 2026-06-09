# VidNotificationDispatcher::RegisterHypervisorRestartHandler(uint,void *,IVndCallback &,void * &)

- ea: `0x14028219c`
- end: `0x140282369`
- name: `?RegisterHypervisorRestartHandler@VidNotificationDispatcher@@QEAAJIPEAXAEAUIVndCallback@@AEAPEAX@Z`
- size: `461`
- prototype: `__int64 __usercall@<rax>(VidNotificationDispatcher *__hidden this@<rcx>, unsigned int@<edx>, void *@<r8>, struct IVndCallback *@<r9>, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14027f740`

## callees

- `0x140035238`
- `0x140035c9c`
- `0x1400364a0`
- `0x1400544a8`
- `0x14008a328`
- `0x1400ba144`
- `0x1400cb87c`
- `0x1402816b0`
- `0x14028219c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140282238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402822cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140282238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1402822cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402821c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1402821c5`
- `vid!VidRegisterHypervisorRestartHandler` at `0x1402822bc`
- `vid!VidRegisterHypervisorRestartHandler` at `0x1402822bc`

## string_xrefs

- `0x140282357`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```

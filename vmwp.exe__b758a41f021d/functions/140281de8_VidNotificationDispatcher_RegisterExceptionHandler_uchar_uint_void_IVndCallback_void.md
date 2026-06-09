# VidNotificationDispatcher::RegisterExceptionHandler(uchar,uint,void *,IVndCallback &,void * &)

- ea: `0x140281de8`
- end: `0x140281fc2`
- name: `?RegisterExceptionHandler@VidNotificationDispatcher@@QEAAJEIPEAXAEAUIVndCallback@@AEAPEAX@Z`
- size: `474`
- prototype: `__int64 __usercall@<rax>(VidNotificationDispatcher *__hidden this@<rcx>, unsigned __int8@<dl>, unsigned int@<r8d>, void *@<r9>, struct IVndCallback *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14027f720`

## callees

- `0x140035238`
- `0x140035c9c`
- `0x1400364a0`
- `0x1400544a8`
- `0x14008a328`
- `0x1400ba144`
- `0x1400cb87c`
- `0x1402816b0`
- `0x140281de8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140281e89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140281f25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140281e89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140281f25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140281e11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140281e11`
- `vid!VidRegisterExceptionHandler` at `0x140281f15`
- `vid!VidRegisterExceptionHandler` at `0x140281f15`

## string_xrefs

- `0x140281fb0`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```

# VidNotificationDispatcher::RegisterExceptionHandler(uchar,uint,void *,IVndCallback &,void * &)

- ea: `0x14027bad8`
- end: `0x14027bcb2`
- name: `?RegisterExceptionHandler@VidNotificationDispatcher@@QEAAJEIPEAXAEAUIVndCallback@@AEAPEAX@Z`
- size: `474`
- prototype: `__int64 __usercall@<rax>(VidNotificationDispatcher *__hidden this@<rcx>, unsigned __int8@<dl>, unsigned int@<r8d>, void *@<r9>, struct IVndCallback *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1402795c0`

## callees

- `0x140040ff8`
- `0x140041a5c`
- `0x140042260`
- `0x14005497c`
- `0x140078cb8`
- `0x14009d7cc`
- `0x1400db410`
- `0x14027b3a0`
- `0x14027bad8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bb79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bc15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bb79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bc15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027bb01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027bb01`
- `vid!VidRegisterExceptionHandler` at `0x14027bc05`
- `vid!VidRegisterExceptionHandler` at `0x14027bc05`

## string_xrefs

- `0x14027bca0`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```

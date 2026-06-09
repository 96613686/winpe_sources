# VidNotificationDispatcher::RegisterGhciInterceptHandler(uint,void *,IVndCallback &,void * &)

- ea: `0x14027bcb8`
- end: `0x14027be85`
- name: `?RegisterGhciInterceptHandler@VidNotificationDispatcher@@QEAAJIPEAXAEAUIVndCallback@@AEAPEAX@Z`
- size: `461`
- prototype: `__int64 __usercall@<rax>(VidNotificationDispatcher *__hidden this@<rcx>, unsigned int@<edx>, void *@<r8>, struct IVndCallback *@<r9>, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1402795d0`

## callees

- `0x140040ff8`
- `0x140041a5c`
- `0x140042260`
- `0x14005497c`
- `0x140078cb8`
- `0x14009d7cc`
- `0x1400db410`
- `0x14027b3a0`
- `0x14027bcb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bd54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bde8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bd54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027bde8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027bce1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14027bce1`
- `vid!VidRegisterGhciInterceptHandler` at `0x14027bdd8`
- `vid!VidRegisterGhciInterceptHandler` at `0x14027bdd8`

## string_xrefs

- `0x14027be73`: `onecore\vm\common\vml\VmReaderWriterLock.h`

## pseudocode

```c

```

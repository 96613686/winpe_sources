# NvIoShutdownWorkerQueue

- ea: `0x1401bb6a4`
- end: `0x1401bb857`
- name: `NvIoShutdownWorkerQueue`
- size: `435`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14007f200`
- `0x1400fc970`
- `0x1400fe920`
- `0x140105aac`
- `0x140106248`
- `0x14015ba7c`

## callees

- `0x140050bd8`
- `0x1400632fc`
- `0x1401bb610`
- `0x1401bb6a4`
- `0x1401bb860`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x1401bb74a`
- `ntoskrnl!KeReleaseSemaphore` at `0x1401bb74a`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1401bb805`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1401bb805`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401bb711`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401bb7e4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401bb711`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401bb7e4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401bb6d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401bb787`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401bb6d7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401bb787`
- `ntoskrnl!ObfDereferenceObject` at `0x1401bb769`
- `ntoskrnl!ObfDereferenceObject` at `0x1401bb83f`
- `ntoskrnl!ObfDereferenceObject` at `0x1401bb769`
- `ntoskrnl!ObfDereferenceObject` at `0x1401bb83f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401bb830`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401bb830`

## pseudocode

```c

```

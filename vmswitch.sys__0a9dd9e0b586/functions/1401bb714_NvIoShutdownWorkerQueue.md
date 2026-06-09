# NvIoShutdownWorkerQueue

- ea: `0x1401bb714`
- end: `0x1401bb8c7`
- name: `NvIoShutdownWorkerQueue`
- size: `435`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14007f200`
- `0x1400fc9e0`
- `0x1400fe990`
- `0x140105b1c`
- `0x1401062b8`
- `0x14015baec`

## callees

- `0x140050bd8`
- `0x1400632fc`
- `0x1401bb680`
- `0x1401bb714`
- `0x1401bb8d0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x1401bb7ba`
- `ntoskrnl!KeReleaseSemaphore` at `0x1401bb7ba`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1401bb875`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1401bb875`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401bb781`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401bb854`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401bb781`
- `ntoskrnl!KeReleaseSpinLock` at `0x1401bb854`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401bb747`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401bb7f7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401bb747`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401bb7f7`
- `ntoskrnl!ObfDereferenceObject` at `0x1401bb7d9`
- `ntoskrnl!ObfDereferenceObject` at `0x1401bb8af`
- `ntoskrnl!ObfDereferenceObject` at `0x1401bb7d9`
- `ntoskrnl!ObfDereferenceObject` at `0x1401bb8af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401bb8a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401bb8a0`

## pseudocode

```c

```

# StorNvmeRemoveNotificationCallback

- ea: `0x1400bb700`
- end: `0x1400bb80e`
- name: `StorNvmeRemoveNotificationCallback`
- size: `270`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400bb700`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400bb778`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bb7c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bb778`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bb7c8`
- `ntoskrnl!ExRundownCompleted` at `0x1400bb7a2`
- `ntoskrnl!ExRundownCompleted` at `0x1400bb7a2`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400bb792`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400bb792`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bb714`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400bb714`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bb731`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bb7b1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bb731`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bb7b1`

## pseudocode

```c

```

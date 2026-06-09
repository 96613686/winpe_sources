# RaidAdapterRestartQueues

- ea: `0x14002c1c0`
- end: `0x14002c633`
- name: `RaidAdapterRestartQueues`
- size: `1139`
- prototype: ``
- caller_count: `9`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000f4bc`
- `0x1400135d0`
- `0x14001fe50`
- `0x140048808`
- `0x14008b790`
- `0x14008dca8`
- `0x1400915a0`
- `0x140092410`
- `0x140093144`

## callees

- `0x140022cb0`
- `0x14002c1c0`
- `0x1400313b0`
- `0x140031420`
- `0x14003982c`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14002c572`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c5b5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c572`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002c5b5`
- `ntoskrnl!KeLowerIrql` at `0x14002c514`
- `ntoskrnl!KeLowerIrql` at `0x14002c514`
- `ntoskrnl!KfRaiseIrql` at `0x14002c2ed`
- `ntoskrnl!KfRaiseIrql` at `0x14002c2ed`
- `ntoskrnl!IoQueueWorkItem` at `0x14002c5a0`
- `ntoskrnl!IoQueueWorkItem` at `0x14002c5a0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002c279`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002c279`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002c48b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002c48b`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002c308`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002c308`
- `ntoskrnl!ExRundownCompleted` at `0x14002c336`
- `ntoskrnl!ExRundownCompleted` at `0x14002c336`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002c326`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002c326`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14002c3fb`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14002c3fb`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002c2cf`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002c2cf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c541`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002c541`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002c61e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002c61e`

## pseudocode

```c

```

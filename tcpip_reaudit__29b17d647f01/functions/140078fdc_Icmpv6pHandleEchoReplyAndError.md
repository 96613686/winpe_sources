# Icmpv6pHandleEchoReplyAndError

- ea: `0x140078fdc`
- end: `0x140079366`
- name: `Icmpv6pHandleEchoReplyAndError`
- size: `906`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140121e50`
- `0x140147aa0`

## callees

- `0x140063ec4`
- `0x140078fdc`
- `0x140079c88`
- `0x140079ce0`
- `0x140079e04`
- `0x140079e3c`
- `0x140079f64`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x140079150`
- `ntoskrnl!MmUnlockPages` at `0x140079150`
- `ntoskrnl!IoFreeMdl` at `0x140079160`
- `ntoskrnl!IoFreeMdl` at `0x140079160`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140079070`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140079083`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140079070`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140079083`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400790b5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400790c8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400790b5`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400790c8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079195`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400791cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400792f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007932c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079195`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400791cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400792f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007932c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079034`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079304`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079034`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079304`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x1400790a2`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x1400790a2`
- `NETIO!RtlCopyMdlToMdl` at `0x1400792bb`
- `NETIO!RtlCopyMdlToMdl` at `0x1400792bb`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400792d9`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400792d9`
- `HAL!KeQueryPerformanceCounter` at `0x140079236`
- `HAL!KeQueryPerformanceCounter` at `0x140079236`

## pseudocode

```c

```

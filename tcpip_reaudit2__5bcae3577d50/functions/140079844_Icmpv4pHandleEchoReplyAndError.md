# Icmpv4pHandleEchoReplyAndError

- ea: `0x140079844`
- end: `0x140079c80`
- name: `Icmpv4pHandleEchoReplyAndError`
- size: `1084`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140079370`
- `0x140145570`

## callees

- `0x140063ec4`
- `0x140079844`
- `0x140079c88`
- `0x140079ce0`
- `0x140079e04`
- `0x140079e3c`
- `0x140079f64`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x140079a96`
- `ntoskrnl!MmUnlockPages` at `0x140079a96`
- `ntoskrnl!IoFreeMdl` at `0x140079aa6`
- `ntoskrnl!IoFreeMdl` at `0x140079aa6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400798d8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400798eb`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400798d8`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400798eb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14007991d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140079930`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14007991d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140079930`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079adb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079b63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079bc5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079c00`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079adb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079b63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079bc5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140079c00`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007989c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079bd8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14007989c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140079bd8`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x14007990a`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x14007990a`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140079c6f`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140079c6f`
- `NETIO!RtlCopyMdlToMdl` at `0x140079a77`
- `NETIO!RtlCopyMdlToMdl` at `0x140079a77`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140079b48`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140079b48`
- `HAL!KeQueryPerformanceCounter` at `0x1400799a3`
- `HAL!KeQueryPerformanceCounter` at `0x1400799a3`

## pseudocode

```c

```

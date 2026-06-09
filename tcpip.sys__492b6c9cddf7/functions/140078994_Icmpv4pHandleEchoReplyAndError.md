# Icmpv4pHandleEchoReplyAndError

- ea: `0x140078994`
- end: `0x140078dd0`
- name: `Icmpv4pHandleEchoReplyAndError`
- size: `1084`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400784c0`
- `0x1401453e0`

## callees

- `0x140063c24`
- `0x140078994`
- `0x140078dd8`
- `0x140078e30`
- `0x140078f54`
- `0x140078f8c`
- `0x1400790b4`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x140078be6`
- `ntoskrnl!MmUnlockPages` at `0x140078be6`
- `ntoskrnl!IoFreeMdl` at `0x140078bf6`
- `ntoskrnl!IoFreeMdl` at `0x140078bf6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140078a28`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140078a3b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140078a28`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140078a3b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140078a6d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140078a80`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140078a6d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140078a80`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078c2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078cb3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078d15`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078d50`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078c2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078cb3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078d15`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078d50`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400789ec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140078d28`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400789ec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140078d28`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x140078a5a`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x140078a5a`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140078dbf`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140078dbf`
- `NETIO!RtlCopyMdlToMdl` at `0x140078bc7`
- `NETIO!RtlCopyMdlToMdl` at `0x140078bc7`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140078c98`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140078c98`
- `HAL!KeQueryPerformanceCounter` at `0x140078af3`
- `HAL!KeQueryPerformanceCounter` at `0x140078af3`

## pseudocode

```c

```

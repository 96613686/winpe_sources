# Icmpv6pHandleEchoReplyAndError

- ea: `0x14007812c`
- end: `0x1400784b6`
- name: `Icmpv6pHandleEchoReplyAndError`
- size: `906`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140121d10`
- `0x140147910`

## callees

- `0x140063c24`
- `0x14007812c`
- `0x140078dd8`
- `0x140078e30`
- `0x140078f54`
- `0x140078f8c`
- `0x1400790b4`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x1400782a0`
- `ntoskrnl!MmUnlockPages` at `0x1400782a0`
- `ntoskrnl!IoFreeMdl` at `0x1400782b0`
- `ntoskrnl!IoFreeMdl` at `0x1400782b0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400781c0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400781d3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400781c0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400781d3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140078205`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140078218`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140078205`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140078218`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400782e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007831c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078441`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007847c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400782e5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007831c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140078441`
- `ntoskrnl!KeReleaseSpinLock` at `0x14007847c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140078184`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140078454`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140078184`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140078454`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x1400781f2`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x1400781f2`
- `NETIO!RtlCopyMdlToMdl` at `0x14007840b`
- `NETIO!RtlCopyMdlToMdl` at `0x14007840b`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140078429`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140078429`
- `HAL!KeQueryPerformanceCounter` at `0x140078386`
- `HAL!KeQueryPerformanceCounter` at `0x140078386`

## pseudocode

```c

```

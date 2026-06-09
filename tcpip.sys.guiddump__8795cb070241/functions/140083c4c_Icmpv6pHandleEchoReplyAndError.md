# Icmpv6pHandleEchoReplyAndError

- ea: `0x140083c4c`
- end: `0x140083fd6`
- name: `Icmpv6pHandleEchoReplyAndError`
- size: `906`
- prototype: `void __fastcall(unsigned __int8, unsigned __int8, unsigned int, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400e18b0`
- `0x14012c4b0`

## callees

- `0x14007fd74`
- `0x140083c4c`
- `0x1400848f8`
- `0x140084950`
- `0x140084a74`
- `0x140084aac`
- `0x140084bd4`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x140083dc0`
- `ntoskrnl!MmUnlockPages` at `0x140083dc0`
- `ntoskrnl!IoFreeMdl` at `0x140083dd0`
- `ntoskrnl!IoFreeMdl` at `0x140083dd0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140083ce0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140083cf3`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140083ce0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140083cf3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140083d25`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140083d38`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140083d25`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140083d38`
- `ntoskrnl!KeReleaseSpinLock` at `0x140083e05`
- `ntoskrnl!KeReleaseSpinLock` at `0x140083e3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140083f61`
- `ntoskrnl!KeReleaseSpinLock` at `0x140083f9c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140083e05`
- `ntoskrnl!KeReleaseSpinLock` at `0x140083e3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140083f61`
- `ntoskrnl!KeReleaseSpinLock` at `0x140083f9c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140083ca4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140083f74`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140083ca4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140083f74`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x140083d12`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x140083d12`
- `NETIO!RtlCopyMdlToMdl` at `0x140083f2b`
- `NETIO!RtlCopyMdlToMdl` at `0x140083f2b`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140083f49`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140083f49`
- `HAL!KeQueryPerformanceCounter` at `0x140083ea6`
- `HAL!KeQueryPerformanceCounter` at `0x140083ea6`

## pseudocode

```c

```

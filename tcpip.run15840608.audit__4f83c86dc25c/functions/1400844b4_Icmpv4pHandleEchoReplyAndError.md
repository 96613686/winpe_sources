# Icmpv4pHandleEchoReplyAndError

- ea: `0x1400844b4`
- end: `0x1400848f0`
- name: `Icmpv4pHandleEchoReplyAndError`
- size: `1084`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x140083880`
- `0x140083fe0`

## callees

- `0x14007fd74`
- `0x1400844b4`
- `0x1400848f8`
- `0x140084950`
- `0x140084a74`
- `0x140084aac`
- `0x140084bd4`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x140084706`
- `ntoskrnl!MmUnlockPages` at `0x140084706`
- `ntoskrnl!IoFreeMdl` at `0x140084716`
- `ntoskrnl!IoFreeMdl` at `0x140084716`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140084548`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14008455b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140084548`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14008455b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14008458d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400845a0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14008458d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400845a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008474b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400847d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140084835`
- `ntoskrnl!KeReleaseSpinLock` at `0x140084870`
- `ntoskrnl!KeReleaseSpinLock` at `0x14008474b`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400847d3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140084835`
- `ntoskrnl!KeReleaseSpinLock` at `0x140084870`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008450c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140084848`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008450c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140084848`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x14008457a`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x14008457a`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x1400848df`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x1400848df`
- `NETIO!RtlCopyMdlToMdl` at `0x1400846e7`
- `NETIO!RtlCopyMdlToMdl` at `0x1400846e7`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400847b8`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400847b8`
- `HAL!KeQueryPerformanceCounter` at `0x140084613`
- `HAL!KeQueryPerformanceCounter` at `0x140084613`

## pseudocode

```c

```

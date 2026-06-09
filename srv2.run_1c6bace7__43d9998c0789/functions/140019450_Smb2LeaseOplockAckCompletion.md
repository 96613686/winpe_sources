# Smb2LeaseOplockAckCompletion

- ea: `0x140019450`
- end: `0x14001957d`
- name: `Smb2LeaseOplockAckCompletion`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000e340`
- `0x140019450`
- `0x14001b3fc`
- `0x14002d4dc`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14003d233`
- `ntoskrnl!IoFreeMdl` at `0x14003d233`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400194ec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400194ec`
- `ntoskrnl!ObfDereferenceObject` at `0x14001949f`
- `ntoskrnl!ObfDereferenceObject` at `0x14001949f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003d1ea`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003d1ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019552`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019552`
- `ntoskrnl!IoFreeIrp` at `0x1400194cb`
- `ntoskrnl!IoFreeIrp` at `0x1400194cb`
- `ntoskrnl!MmUnlockPages` at `0x14003d224`
- `ntoskrnl!MmUnlockPages` at `0x14003d224`

## pseudocode

```c

```

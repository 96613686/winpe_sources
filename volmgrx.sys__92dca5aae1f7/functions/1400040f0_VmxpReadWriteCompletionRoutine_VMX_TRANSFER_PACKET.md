# VmxpReadWriteCompletionRoutine(VMX_TRANSFER_PACKET *)

- ea: `0x1400040f0`
- end: `0x1400042a4`
- name: `?VmxpReadWriteCompletionRoutine@@YAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `436`
- prototype: `void __fastcall(struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002470`
- `0x1400040f0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004159`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004159`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004196`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004293`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004196`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004293`

## pseudocode

```c

```

# Rct::SequenceTable::LockAcquiredForShrink(AE_ENVIRON *,AE_COMPLETION_CONTEXT *,AE_TODO *)

- ea: `0x140024ab0`
- end: `0x140024cf8`
- name: `?LockAcquiredForShrink@SequenceTable@Rct@@CAXPEAUAE_ENVIRON@@PEAUAE_COMPLETION_CONTEXT@@PEAUAE_TODO@@@Z`
- size: `584`
- prototype: `void __fastcall(struct AE_ENVIRON *, struct AE_COMPLETION_CONTEXT *, struct AE_TODO *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140024ab0`
- `0x140024e5c`
- `0x14002684c`
- `0x140028554`
- `0x140059214`
- `0x14005a5b8`
- `0x14005a8cc`
- `0x14005ccac`
- `0x14005cd6c`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140024b9b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140024c45`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140024c87`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140024b9b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140024c45`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140024c87`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140024bb6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140024c5c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140024cd3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140024bb6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140024c5c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140024cd3`

## pseudocode

```c

```

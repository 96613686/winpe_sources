# Rct::SequenceTable::LockAcquiredForShrink(AE_ENVIRON *,AE_COMPLETION_CONTEXT *,AE_TODO *)

- ea: `0x140024690`
- end: `0x1400248d8`
- name: `?LockAcquiredForShrink@SequenceTable@Rct@@CAXPEAUAE_ENVIRON@@PEAUAE_COMPLETION_CONTEXT@@PEAUAE_TODO@@@Z`
- size: `584`
- prototype: `void __fastcall(struct AE_ENVIRON *, struct AE_COMPLETION_CONTEXT *, struct AE_TODO *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140024690`
- `0x140024a3c`
- `0x14002642c`
- `0x140028034`
- `0x140058e24`
- `0x14005a1c8`
- `0x14005a4dc`
- `0x14005c8bc`
- `0x14005c97c`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002477b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140024825`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140024867`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002477b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140024825`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140024867`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140024796`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002483c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400248b3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140024796`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002483c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400248b3`

## pseudocode

```c

```

# Rct::SequenceTable::GotRangeLock(AE_ENVIRON *,AE_COMPLETION_CONTEXT *,AE_TODO *)

- ea: `0x14005a630`
- end: `0x14005a6dc`
- name: `?GotRangeLock@SequenceTable@Rct@@CAXPEAUAE_ENVIRON@@PEAUAE_COMPLETION_CONTEXT@@PEAUAE_TODO@@@Z`
- size: `172`
- prototype: `static void(struct AE_ENVIRON *, struct AE_COMPLETION_CONTEXT *, struct AE_TODO *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14005a630`
- `0x14005b6f4`
- `0x14005b88c`
- `0x14005b978`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a674`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a674`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a6a3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a6b1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a6a3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a6b1`

## pseudocode

```c

```

# Rct::SequenceTable::GotRangeLock(AE_ENVIRON *,AE_COMPLETION_CONTEXT *,AE_TODO *)

- ea: `0x14005a240`
- end: `0x14005a2ec`
- name: `?GotRangeLock@SequenceTable@Rct@@CAXPEAUAE_ENVIRON@@PEAUAE_COMPLETION_CONTEXT@@PEAUAE_TODO@@@Z`
- size: `172`
- prototype: `void __fastcall(struct AE_ENVIRON *, struct AE_COMPLETION_CONTEXT *, struct AE_TODO *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14005a240`
- `0x14005b304`
- `0x14005b49c`
- `0x14005b588`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a284`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a284`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a2b3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a2c1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a2b3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a2c1`

## pseudocode

```c

```

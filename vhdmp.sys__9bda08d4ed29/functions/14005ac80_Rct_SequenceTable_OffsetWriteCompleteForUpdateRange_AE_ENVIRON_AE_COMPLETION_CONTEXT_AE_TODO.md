# Rct::SequenceTable::OffsetWriteCompleteForUpdateRange(AE_ENVIRON *,AE_COMPLETION_CONTEXT *,AE_TODO *)

- ea: `0x14005ac80`
- end: `0x14005ae4f`
- name: `?OffsetWriteCompleteForUpdateRange@SequenceTable@Rct@@CAXPEAUAE_ENVIRON@@PEAUAE_COMPLETION_CONTEXT@@PEAUAE_TODO@@@Z`
- size: `463`
- prototype: `static void(struct AE_ENVIRON *, struct AE_COMPLETION_CONTEXT *, struct AE_TODO *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400029f4`
- `0x14005ac80`
- `0x14005b324`
- `0x14005b88c`
- `0x14005b978`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005acf7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005add1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005acf7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005add1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005ad57`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005ae12`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005ad57`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005ae12`

## pseudocode

```c

```

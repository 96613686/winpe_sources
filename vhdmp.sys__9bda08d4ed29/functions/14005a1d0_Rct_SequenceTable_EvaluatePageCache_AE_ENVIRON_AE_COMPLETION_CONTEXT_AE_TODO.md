# Rct::SequenceTable::EvaluatePageCache(AE_ENVIRON *,AE_COMPLETION_CONTEXT *,AE_TODO *)

- ea: `0x14005a1d0`
- end: `0x14005a4a3`
- name: `?EvaluatePageCache@SequenceTable@Rct@@CAXPEAUAE_ENVIRON@@PEAUAE_COMPLETION_CONTEXT@@PEAUAE_TODO@@@Z`
- size: `723`
- prototype: `void __fastcall(struct AE_ENVIRON *, struct AE_COMPLETION_CONTEXT *, struct AE_TODO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14005a6e4`

## callees

- `0x14001ebb4`
- `0x140059078`
- `0x1400590a0`
- `0x14005a1d0`
- `0x14005b324`
- `0x14005dbb0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a238`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005a238`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a47c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a47c`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14005a213`
- `ntoskrnl!ZwQuerySystemInformation` at `0x14005a213`
- `ntoskrnl!KeSetEvent` at `0x14005a458`
- `ntoskrnl!KeSetEvent` at `0x14005a458`

## pseudocode

```c

```

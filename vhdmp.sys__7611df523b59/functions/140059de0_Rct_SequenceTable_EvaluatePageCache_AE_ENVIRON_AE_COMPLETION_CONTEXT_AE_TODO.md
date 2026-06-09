# Rct::SequenceTable::EvaluatePageCache(AE_ENVIRON *,AE_COMPLETION_CONTEXT *,AE_TODO *)

- ea: `0x140059de0`
- end: `0x14005a0b3`
- name: `?EvaluatePageCache@SequenceTable@Rct@@CAXPEAUAE_ENVIRON@@PEAUAE_COMPLETION_CONTEXT@@PEAUAE_TODO@@@Z`
- size: `723`
- prototype: `void __fastcall(struct AE_ENVIRON *, struct AE_COMPLETION_CONTEXT *, struct AE_TODO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14005a2f4`

## callees

- `0x14001e794`
- `0x140058c88`
- `0x140058cb0`
- `0x140059de0`
- `0x14005af34`
- `0x14005d7c0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140059e48`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140059e48`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a08c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005a08c`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140059e23`
- `ntoskrnl!ZwQuerySystemInformation` at `0x140059e23`
- `ntoskrnl!KeSetEvent` at `0x14005a068`
- `ntoskrnl!KeSetEvent` at `0x14005a068`

## pseudocode

```c

```

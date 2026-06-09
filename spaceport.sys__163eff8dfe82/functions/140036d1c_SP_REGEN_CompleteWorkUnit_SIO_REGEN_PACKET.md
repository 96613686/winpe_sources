# SP_REGEN::CompleteWorkUnit(SIO_REGEN_PACKET *)

- ea: `0x140036d1c`
- end: `0x140036e84`
- name: `?CompleteWorkUnit@SP_REGEN@@AEAAXPEAVSIO_REGEN_PACKET@@@Z`
- size: `360`
- prototype: `void __fastcall(SP_REGEN *__hidden this, struct SIO_REGEN_PACKET *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140038800`

## callees

- `0x140036d1c`
- `0x140038f0c`
- `0x140039110`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140036da8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140036da8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036e5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036e5a`
- `ntoskrnl!RtlInitializeBitMap` at `0x140036e6e`
- `ntoskrnl!RtlInitializeBitMap` at `0x140036e6e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140036dda`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140036dda`

## pseudocode

```c

```

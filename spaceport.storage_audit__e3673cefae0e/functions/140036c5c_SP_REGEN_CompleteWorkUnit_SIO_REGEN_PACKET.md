# SP_REGEN::CompleteWorkUnit(SIO_REGEN_PACKET *)

- ea: `0x140036c5c`
- end: `0x140036dc4`
- name: `?CompleteWorkUnit@SP_REGEN@@AEAAXPEAVSIO_REGEN_PACKET@@@Z`
- size: `360`
- prototype: `void __fastcall(SP_REGEN *__hidden this, struct SIO_REGEN_PACKET *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140038740`

## callees

- `0x140036c5c`
- `0x140038e4c`
- `0x140039050`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140036ce8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140036ce8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036d9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036d9a`
- `ntoskrnl!RtlInitializeBitMap` at `0x140036dae`
- `ntoskrnl!RtlInitializeBitMap` at `0x140036dae`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140036d1a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140036d1a`

## pseudocode

```c

```

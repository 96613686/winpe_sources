# AeSignalCompletionWithStatus

- ea: `0x140004b34`
- end: `0x140004d2b`
- name: `AeSignalCompletionWithStatus`
- size: `503`
- prototype: `__int64 __fastcall(PKSPIN_LOCK SpinLock)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14003f3e0`
- `0x1400406a0`
- `0x1400519f0`
- `0x1400c4948`
- `0x1400c5f98`
- `0x1400d773c`
- `0x1400d8740`

## callees

- `0x140004b34`
- `0x140005000`
- `0x140006010`
- `0x14005d840`

## import_xrefs

- `ntoskrnl!ExTryQueueWorkItem` at `0x140004cba`
- `ntoskrnl!ExTryQueueWorkItem` at `0x140004cba`
- `ntoskrnl!KeInsertQueue` at `0x140004cd5`
- `ntoskrnl!KeInsertQueue` at `0x140004cd5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140004bf1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140004bf1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004c6c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140004c6c`

## pseudocode

```c

```

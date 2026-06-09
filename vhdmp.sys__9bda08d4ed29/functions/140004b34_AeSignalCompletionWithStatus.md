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

- `0x14003f7d0`
- `0x140040a90`
- `0x140051de0`
- `0x1400c4938`
- `0x1400c5f88`
- `0x1400d76cc`
- `0x1400d86d0`

## callees

- `0x140004b34`
- `0x140005000`
- `0x140006010`
- `0x14005dc30`

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

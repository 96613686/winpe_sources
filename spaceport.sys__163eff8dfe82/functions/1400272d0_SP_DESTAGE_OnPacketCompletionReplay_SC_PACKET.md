# SP_DESTAGE::OnPacketCompletionReplay(SC_PACKET *)

- ea: `0x1400272d0`
- end: `0x1400273fc`
- name: `?OnPacketCompletionReplay@SP_DESTAGE@@QEAAJPEAVSC_PACKET@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(SP_DESTAGE *__hidden this, struct SC_PACKET *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140037450`

## callees

- `0x1400272d0`
- `0x140027404`
- `0x140068150`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140027329`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140027329`
- `ntoskrnl!KeSetEvent` at `0x1400273ac`
- `ntoskrnl!KeSetEvent` at `0x1400273ac`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002736d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002736d`

## pseudocode

```c

```

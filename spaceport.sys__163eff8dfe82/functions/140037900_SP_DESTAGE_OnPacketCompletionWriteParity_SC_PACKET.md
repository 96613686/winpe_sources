# SP_DESTAGE::OnPacketCompletionWriteParity(SC_PACKET *)

- ea: `0x140037900`
- end: `0x140037a84`
- name: `?OnPacketCompletionWriteParity@SP_DESTAGE@@QEAAJPEAVSC_PACKET@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(SP_DESTAGE *__hidden this, struct SC_PACKET *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140037450`

## callees

- `0x140027404`
- `0x140037900`
- `0x140068150`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400379c9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400379c9`
- `ntoskrnl!KeSetEvent` at `0x140037987`
- `ntoskrnl!KeSetEvent` at `0x140037a65`
- `ntoskrnl!KeSetEvent` at `0x140037987`
- `ntoskrnl!KeSetEvent` at `0x140037a65`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140037a1d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140037a1d`

## pseudocode

```c

```

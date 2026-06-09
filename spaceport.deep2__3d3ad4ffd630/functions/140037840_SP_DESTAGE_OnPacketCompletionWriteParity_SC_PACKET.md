# SP_DESTAGE::OnPacketCompletionWriteParity(SC_PACKET *)

- ea: `0x140037840`
- end: `0x1400379c4`
- name: `?OnPacketCompletionWriteParity@SP_DESTAGE@@QEAAJPEAVSC_PACKET@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(SP_DESTAGE *__hidden this, struct SC_PACKET *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140037390`

## callees

- `0x140027404`
- `0x140037840`
- `0x140068000`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140037909`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140037909`
- `ntoskrnl!KeSetEvent` at `0x1400378c7`
- `ntoskrnl!KeSetEvent` at `0x1400379a5`
- `ntoskrnl!KeSetEvent` at `0x1400378c7`
- `ntoskrnl!KeSetEvent` at `0x1400379a5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003795d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003795d`

## pseudocode

```c

```

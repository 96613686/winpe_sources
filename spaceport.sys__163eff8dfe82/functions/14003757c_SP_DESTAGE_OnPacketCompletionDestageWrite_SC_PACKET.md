# SP_DESTAGE::OnPacketCompletionDestageWrite(SC_PACKET *)

- ea: `0x14003757c`
- end: `0x1400376b4`
- name: `?OnPacketCompletionDestageWrite@SP_DESTAGE@@QEAAJPEAVSC_PACKET@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(SP_DESTAGE *__hidden this, struct SC_PACKET *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140037450`

## callees

- `0x140027404`
- `0x14003757c`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400375eb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400375eb`
- `ntoskrnl!KeSetEvent` at `0x14003767d`
- `ntoskrnl!KeSetEvent` at `0x14003767d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140037639`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140037639`

## pseudocode

```c

```

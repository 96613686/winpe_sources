# SP_DESTAGE::OnPacketCompletionDestageWrite(SC_PACKET *)

- ea: `0x1400374bc`
- end: `0x1400375f4`
- name: `?OnPacketCompletionDestageWrite@SP_DESTAGE@@QEAAJPEAVSC_PACKET@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(SP_DESTAGE *__hidden this, struct SC_PACKET *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140037390`

## callees

- `0x140027404`
- `0x1400374bc`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003752b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003752b`
- `ntoskrnl!KeSetEvent` at `0x1400375bd`
- `ntoskrnl!KeSetEvent` at `0x1400375bd`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140037579`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140037579`

## pseudocode

```c

```

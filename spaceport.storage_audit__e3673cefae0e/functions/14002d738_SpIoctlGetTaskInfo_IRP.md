# SpIoctlGetTaskInfo(_IRP *)

- ea: `0x14002d738`
- end: `0x14002d999`
- name: `?SpIoctlGetTaskInfo@@YAJPEAU_IRP@@@Z`
- size: `609`
- prototype: `__int64 __fastcall(struct _IRP *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x1400b57b0`

## callees

- `0x14001d3f0`
- `0x14002ce90`
- `0x14002d280`
- `0x14002d3fc`
- `0x14002d738`
- `0x14002e43c`
- `0x140037028`
- `0x1400684c0`
- `0x1400b55b0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002d838`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002d838`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002d8e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002d8e5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d8d9`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d8d9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002d87e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002d87e`

## pseudocode

```c

```

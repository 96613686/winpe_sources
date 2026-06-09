# SP_TASK::GetIds(_GUID,_GUID * const,ulong,ulong *)

- ea: `0x140036f5c`
- end: `0x140037022`
- name: `?GetIds@SP_TASK@@QEAAXU_GUID@@QEAU2@KPEAK@Z`
- size: `198`
- prototype: `void(SP_TASK *__hidden this, struct _GUID *__struct_ptr, struct _GUID *const, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14002d9a0`

## callees

- `0x140036f5c`
- `0x1400680a0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140036f9d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140036f9d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140037003`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140037003`

## pseudocode

```c

```

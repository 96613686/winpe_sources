# SP_TASK::GetIds(_GUID,_GUID * const,ulong,ulong *)

- ea: `0x14003701c`
- end: `0x1400370e2`
- name: `?GetIds@SP_TASK@@QEAAXU_GUID@@QEAU2@KPEAK@Z`
- size: `198`
- prototype: `void(SP_TASK *__hidden this, struct _GUID *__struct_ptr, struct _GUID *const, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14002d9a0`

## callees

- `0x14003701c`
- `0x1400681e0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003705d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003705d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400370c3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400370c3`

## pseudocode

```c

```

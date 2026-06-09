# SP_TASK::GetInfo(_SP_TASK_INFO *)

- ea: `0x1400370e8`
- end: `0x14003723c`
- name: `?GetInfo@SP_TASK@@QEAAEPEAU_SP_TASK_INFO@@@Z`
- size: `340`
- prototype: `unsigned __int8 __fastcall(SP_TASK *__hidden this, struct _SP_TASK_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14002d738`

## callees

- `0x140019060`
- `0x1400370e8`
- `0x140068150`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140037116`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140037116`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003721f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003721f`

## pseudocode

```c

```

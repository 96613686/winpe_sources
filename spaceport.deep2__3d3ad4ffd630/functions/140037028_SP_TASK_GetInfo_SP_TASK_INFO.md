# SP_TASK::GetInfo(_SP_TASK_INFO *)

- ea: `0x140037028`
- end: `0x14003717c`
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
- `0x140037028`
- `0x140068000`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140037056`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140037056`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003715f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003715f`

## pseudocode

```c

```

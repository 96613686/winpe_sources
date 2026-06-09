# SP_TASK::Insert(SP_TASK_CONTEXT *)

- ea: `0x140028a4c`
- end: `0x140028b02`
- name: `?Insert@SP_TASK@@QEAAXPEAVSP_TASK_CONTEXT@@@Z`
- size: `182`
- prototype: `void __fastcall(SP_TASK *__hidden this, struct SP_TASK_CONTEXT *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14002f450`
- `0x14009d114`

## callees

- `0x140028a4c`
- `0x140028b08`
- `0x140068000`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140028a83`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140028a83`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140028ada`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140028ada`

## pseudocode

```c

```

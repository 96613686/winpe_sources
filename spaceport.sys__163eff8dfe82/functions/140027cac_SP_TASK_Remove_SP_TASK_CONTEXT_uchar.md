# SP_TASK::Remove(SP_TASK_CONTEXT *,uchar)

- ea: `0x140027cac`
- end: `0x140027d69`
- name: `?Remove@SP_TASK@@QEAAXPEAVSP_TASK_CONTEXT@@E@Z`
- size: `189`
- prototype: `void __fastcall(SP_TASK *__hidden this, struct SP_TASK_CONTEXT *, unsigned __int8)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x140027830`
- `0x14002f57c`
- `0x140038800`

## callees

- `0x140027cac`
- `0x140068150`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140027cd4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140027cd4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140027d1c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140027d1c`

## pseudocode

```c

```

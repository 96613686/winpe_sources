# SP_POOL::InsertTask(SP_TASK *)

- ea: `0x140028b08`
- end: `0x140028ba7`
- name: `?InsertTask@SP_POOL@@QEAAEPEAVSP_TASK@@@Z`
- size: `159`
- prototype: `unsigned __int8 __fastcall(SP_POOL *__hidden this, struct SP_TASK *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140028a4c`

## callees

- `0x140028b08`
- `0x140028bb0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140028b33`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140028b33`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140028b8c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140028b8c`

## pseudocode

```c

```

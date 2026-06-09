# SP_WORKITEM::RemoveAll(_LIST_ENTRY *)

- ea: `0x14001b370`
- end: `0x14001b4a0`
- name: `?RemoveAll@SP_WORKITEM@@QEAAEPEAU_LIST_ENTRY@@@Z`
- size: `304`
- prototype: `unsigned __int8 __fastcall(SP_WORKITEM *__hidden this, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001b2c0`

## callees

- `0x14001b370`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001b39d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001b39d`
- `ntoskrnl!IoFreeWorkItem` at `0x14001b492`
- `ntoskrnl!IoFreeWorkItem` at `0x14001b492`
- `ntoskrnl!KeSetEvent` at `0x14001b457`
- `ntoskrnl!KeSetEvent` at `0x14001b457`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b46b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001b46b`

## pseudocode

```c

```

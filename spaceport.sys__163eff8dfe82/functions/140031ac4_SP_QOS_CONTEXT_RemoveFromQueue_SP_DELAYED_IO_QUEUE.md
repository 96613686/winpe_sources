# SP_QOS_CONTEXT::RemoveFromQueue(_SP_DELAYED_IO_QUEUE *)

- ea: `0x140031ac4`
- end: `0x140031b4e`
- name: `?RemoveFromQueue@SP_QOS_CONTEXT@@CAPEAU_IRP@@PEAU_SP_DELAYED_IO_QUEUE@@@Z`
- size: `138`
- prototype: `struct _IRP *__fastcall(struct _SP_DELAYED_IO_QUEUE *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140031484`

## callees

- `0x140031ac4`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140031ae5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140031ae5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140031b1f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140031b1f`

## pseudocode

```c

```

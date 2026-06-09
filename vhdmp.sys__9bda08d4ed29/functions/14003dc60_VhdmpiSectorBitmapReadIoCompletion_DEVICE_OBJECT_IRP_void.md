# VhdmpiSectorBitmapReadIoCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14003dc60`
- end: `0x14003decf`
- name: `?VhdmpiSectorBitmapReadIoCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `623`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140016bf8`
- `0x140017000`
- `0x1400205a4`
- `0x1400210f0`
- `0x140023980`
- `0x140027358`
- `0x140036284`
- `0x14003ce6c`
- `0x14003d0f8`
- `0x14003d444`
- `0x14003d9bc`
- `0x14003dc60`
- `0x14003dfb8`
- `0x14003e9fc`
- `0x14003ea38`
- `0x14005de00`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003ddca`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003ddca`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003de18`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003de18`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003de57`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003de57`

## string_xrefs

- `0x14003dcd0`: `VhdmpiSectorBitmapReadIoCompletion`
- `0x14003dcc9`: `VhdmpiSectorBitmapReadIoCompletion: Irp=%p Context=%p`

## pseudocode

```c

```

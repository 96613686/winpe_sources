# VhdmpiSectorBitmapReadIoCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x14003d870`
- end: `0x14003dadf`
- name: `?VhdmpiSectorBitmapReadIoCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `623`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140016758`
- `0x140016b60`
- `0x140020184`
- `0x140020cd0`
- `0x140023560`
- `0x140026e34`
- `0x140035e94`
- `0x14003ca7c`
- `0x14003cd08`
- `0x14003d054`
- `0x14003d5cc`
- `0x14003d870`
- `0x14003dbc8`
- `0x14003e60c`
- `0x14003e648`
- `0x14005da00`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003d9da`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003d9da`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003da28`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003da28`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003da67`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14003da67`

## string_xrefs

- `0x14003d8e0`: `VhdmpiSectorBitmapReadIoCompletion`
- `0x14003d8d9`: `VhdmpiSectorBitmapReadIoCompletion: Irp=%p Context=%p`

## pseudocode

```c

```

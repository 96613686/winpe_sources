# VhdmpiSetZeroDataSyncCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x1400416f0`
- end: `0x14004175c`
- name: `?VhdmpiSetZeroDataSyncCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `108`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400416f0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14004172b`
- `ntoskrnl!IoFreeIrp` at `0x14004172b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004171c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004171c`
- `ntoskrnl!KeSetEvent` at `0x14004173f`
- `ntoskrnl!KeSetEvent` at `0x14004173f`

## pseudocode

```c

```

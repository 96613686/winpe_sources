# VhdmpiSetZeroDataSyncCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140041ae0`
- end: `0x140041b4c`
- name: `?VhdmpiSetZeroDataSyncCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `108`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140041ae0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140041b1b`
- `ntoskrnl!IoFreeIrp` at `0x140041b1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041b0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041b0c`
- `ntoskrnl!KeSetEvent` at `0x140041b2f`
- `ntoskrnl!KeSetEvent` at `0x140041b2f`

## pseudocode

```c

```

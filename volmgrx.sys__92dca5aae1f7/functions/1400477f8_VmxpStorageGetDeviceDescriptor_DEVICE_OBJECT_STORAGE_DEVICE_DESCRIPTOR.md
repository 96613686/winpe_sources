# VmxpStorageGetDeviceDescriptor(_DEVICE_OBJECT *,_STORAGE_DEVICE_DESCRIPTOR * *)

- ea: `0x1400477f8`
- end: `0x14004791b`
- name: `?VmxpStorageGetDeviceDescriptor@@YAJPEAU_DEVICE_OBJECT@@PEAPEAU_STORAGE_DEVICE_DESCRIPTOR@@@Z`
- size: `291`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, struct _STORAGE_DEVICE_DESCRIPTOR **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140033564`

## callees

- `0x14001b960`
- `0x1400477f8`
- `0x14005d644`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140047890`
- `ntoskrnl!ExAllocatePool2` at `0x140047890`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400478eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400478eb`

## pseudocode

```c

```

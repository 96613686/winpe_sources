# VmxpRead(_DEVICE_OBJECT *,unsigned __int64,ulong,uchar * *)

- ea: `0x1400476a8`
- end: `0x1400477f2`
- name: `?VmxpRead@@YAJPEAU_DEVICE_OBJECT@@_KKPEAPEAE@Z`
- size: `330`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, union _LARGE_INTEGER, ULONG, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140034000`

## callees

- `0x1400476a8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400476fa`
- `ntoskrnl!ExAllocatePool2` at `0x1400476fa`
- `ntoskrnl!IofCallDriver` at `0x140047783`
- `ntoskrnl!IofCallDriver` at `0x140047783`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400477c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400477c7`
- `ntoskrnl!KeInitializeEvent` at `0x140047722`
- `ntoskrnl!KeInitializeEvent` at `0x140047722`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400477ae`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400477ae`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x140047765`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x140047765`

## pseudocode

```c

```

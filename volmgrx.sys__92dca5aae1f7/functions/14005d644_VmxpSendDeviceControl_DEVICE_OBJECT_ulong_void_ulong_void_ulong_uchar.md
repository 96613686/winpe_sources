# VmxpSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)

- ea: `0x14005d644`
- end: `0x14005d72b`
- name: `?VmxpSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z`
- size: `231`
- prototype: `NTSTATUS __fastcall(PDEVICE_OBJECT DeviceObject, ULONG IoControlCode, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength, BOOLEAN InternalDeviceIoControl)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x140030110`
- `0x140030a04`
- `0x140031390`
- `0x14003345c`
- `0x14003364c`
- `0x140033750`
- `0x140033854`
- `0x140033958`
- `0x140033b44`
- `0x140033df4`
- `0x1400341a8`
- `0x1400342bc`
- `0x14003a0bc`
- `0x140046dec`
- `0x140046e60`
- `0x1400477f8`
- `0x140053b8c`
- `0x140055f34`
- `0x14005f078`

## callees

- `0x14005d644`

## import_xrefs

- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14005d6c7`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14005d6c7`
- `ntoskrnl!IofCallDriver` at `0x14005d6f0`
- `ntoskrnl!IofCallDriver` at `0x14005d6f0`
- `ntoskrnl!KeInitializeEvent` at `0x14005d679`
- `ntoskrnl!KeInitializeEvent` at `0x14005d679`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005d719`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005d719`

## pseudocode

```c

```

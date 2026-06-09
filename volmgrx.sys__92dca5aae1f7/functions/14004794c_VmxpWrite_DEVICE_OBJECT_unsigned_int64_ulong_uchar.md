# VmxpWrite(_DEVICE_OBJECT *,unsigned __int64,ulong,uchar *)

- ea: `0x14004794c`
- end: `0x140047a3b`
- name: `?VmxpWrite@@YAJPEAU_DEVICE_OBJECT@@_KKPEAE@Z`
- size: `239`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, unsigned __int64, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14003c4b4`

## callees

- `0x14004794c`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400479ef`
- `ntoskrnl!IofCallDriver` at `0x1400479ef`
- `ntoskrnl!KeInitializeEvent` at `0x140047983`
- `ntoskrnl!KeInitializeEvent` at `0x140047983`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047a1a`
- `ntoskrnl!KeWaitForSingleObject` at `0x140047a1a`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1400479c6`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1400479c6`

## pseudocode

```c

```

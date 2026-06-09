# MpReadRawDevice

- ea: `0x14006442c`
- end: `0x14006476e`
- name: `MpReadRawDevice`
- size: `834`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140062588`

## callees

- `0x140005e78`
- `0x14000bf20`
- `0x14000c0d0`
- `0x1400118d0`
- `0x14006442c`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x1400645c2`
- `ntoskrnl!KeResetEvent` at `0x1400645c2`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1400645ff`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1400645ff`
- `ntoskrnl!IofCallDriver` at `0x14006452d`
- `ntoskrnl!IofCallDriver` at `0x140064674`
- `ntoskrnl!IofCallDriver` at `0x14006452d`
- `ntoskrnl!IofCallDriver` at `0x140064674`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400644f1`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400644f1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140064557`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006469e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140064557`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006469e`
- `ntoskrnl!KeInitializeEvent` at `0x1400644a6`
- `ntoskrnl!KeInitializeEvent` at `0x1400644a6`

## pseudocode

```c

```

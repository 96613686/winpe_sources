# MpWriteRawDevice

- ea: `0x14007b978`
- end: `0x14007bb62`
- name: `MpWriteRawDevice`
- size: `490`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14007b770`

## callees

- `0x140005e78`
- `0x14000c0d0`
- `0x1400118d0`
- `0x14007b978`

## import_xrefs

- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x14007b9f6`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x14007b9f6`
- `ntoskrnl!IofCallDriver` at `0x14007ba63`
- `ntoskrnl!IofCallDriver` at `0x14007ba63`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007ba8d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007ba8d`
- `ntoskrnl!KeInitializeEvent` at `0x14007b9bd`
- `ntoskrnl!KeInitializeEvent` at `0x14007b9bd`

## pseudocode

```c

```

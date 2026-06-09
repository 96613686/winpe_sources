# VhdmpiOptimalZeroWrite(_VHD_BACKING_STORE_HEADER *,unsigned __int64,ulong,ulong *)

- ea: `0x1400c8ccc`
- end: `0x1400c8f7c`
- name: `?VhdmpiOptimalZeroWrite@@YAXPEAU_VHD_BACKING_STORE_HEADER@@_KKPEAK@Z`
- size: `688`
- prototype: `void __fastcall(struct _VHD_BACKING_STORE_HEADER *, unsigned __int64, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400c9030`

## callees

- `0x140012fe0`
- `0x140014710`
- `0x140017000`
- `0x1400205f0`
- `0x140033d10`
- `0x1400c8ccc`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x1400c8e46`
- `ntoskrnl!KeClearEvent` at `0x1400c8e46`
- `ntoskrnl!IoFreeIrp` at `0x1400c8f3c`
- `ntoskrnl!IoFreeIrp` at `0x1400c8f3c`
- `ntoskrnl!IoFreeMdl` at `0x1400c8f4b`
- `ntoskrnl!IoFreeMdl` at `0x1400c8f4b`
- `ntoskrnl!IoAllocateMdl` at `0x1400c8d92`
- `ntoskrnl!IoAllocateMdl` at `0x1400c8d92`
- `ntoskrnl!IoReuseIrp` at `0x1400c8e35`
- `ntoskrnl!IoReuseIrp` at `0x1400c8e35`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c8eed`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c8eed`
- `ntoskrnl!KeInitializeEvent` at `0x1400c8d73`
- `ntoskrnl!KeInitializeEvent` at `0x1400c8d73`

## pseudocode

```c

```

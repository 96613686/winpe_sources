# VhdmpiOptimalZeroWrite(_VHD_BACKING_STORE_HEADER *,unsigned __int64,ulong,ulong *)

- ea: `0x1400c8cdc`
- end: `0x1400c8f8c`
- name: `?VhdmpiOptimalZeroWrite@@YAXPEAU_VHD_BACKING_STORE_HEADER@@_KKPEAK@Z`
- size: `688`
- prototype: `void __fastcall(struct _VHD_BACKING_STORE_HEADER *, unsigned __int64, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400c9040`

## callees

- `0x140011cb0`
- `0x140014270`
- `0x140016b60`
- `0x1400201d0`
- `0x140033850`
- `0x1400c8cdc`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x1400c8e56`
- `ntoskrnl!KeClearEvent` at `0x1400c8e56`
- `ntoskrnl!IoFreeIrp` at `0x1400c8f4c`
- `ntoskrnl!IoFreeIrp` at `0x1400c8f4c`
- `ntoskrnl!IoFreeMdl` at `0x1400c8f5b`
- `ntoskrnl!IoFreeMdl` at `0x1400c8f5b`
- `ntoskrnl!IoAllocateMdl` at `0x1400c8da2`
- `ntoskrnl!IoAllocateMdl` at `0x1400c8da2`
- `ntoskrnl!IoReuseIrp` at `0x1400c8e45`
- `ntoskrnl!IoReuseIrp` at `0x1400c8e45`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c8efd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c8efd`
- `ntoskrnl!KeInitializeEvent` at `0x1400c8d83`
- `ntoskrnl!KeInitializeEvent` at `0x1400c8d83`

## pseudocode

```c

```

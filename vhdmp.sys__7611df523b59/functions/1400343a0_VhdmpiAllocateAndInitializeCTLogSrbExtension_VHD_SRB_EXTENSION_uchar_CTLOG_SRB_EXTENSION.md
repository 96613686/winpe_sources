# VhdmpiAllocateAndInitializeCTLogSrbExtension(_VHD_SRB_EXTENSION *,uchar,_CTLOG_SRB_EXTENSION * *)

- ea: `0x1400343a0`
- end: `0x140034547`
- name: `?VhdmpiAllocateAndInitializeCTLogSrbExtension@@YAJPEAU_VHD_SRB_EXTENSION@@EPEAPEAU_CTLOG_SRB_EXTENSION@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(struct _VHD_SRB_EXTENSION *, char, struct _CTLOG_SRB_EXTENSION **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140011f10`

## callees

- `0x140025718`
- `0x14002a47c`
- `0x1400343a0`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1400344ec`
- `ntoskrnl!IoFreeMdl` at `0x1400344ec`
- `ntoskrnl!IoAllocateMdl` at `0x140034446`
- `ntoskrnl!IoAllocateMdl` at `0x140034446`
- `ntoskrnl!IoBuildPartialMdl` at `0x140034470`
- `ntoskrnl!IoBuildPartialMdl` at `0x140034470`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003450b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034527`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003450b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034527`
- `ntoskrnl!ExAllocatePool2` at `0x1400343d8`
- `ntoskrnl!ExAllocatePool2` at `0x1400343d8`

## pseudocode

```c

```

# VhdmpiAllocateAndInitializeCTLogSrbExtension(_VHD_SRB_EXTENSION *,uchar,_CTLOG_SRB_EXTENSION * *)

- ea: `0x140034860`
- end: `0x140034a07`
- name: `?VhdmpiAllocateAndInitializeCTLogSrbExtension@@YAJPEAU_VHD_SRB_EXTENSION@@EPEAPEAU_CTLOG_SRB_EXTENSION@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(struct _VHD_SRB_EXTENSION *, unsigned __int8, struct _CTLOG_SRB_EXTENSION **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140013240`

## callees

- `0x140025b38`
- `0x14002a99c`
- `0x140034860`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x1400349ac`
- `ntoskrnl!IoFreeMdl` at `0x1400349ac`
- `ntoskrnl!IoAllocateMdl` at `0x140034906`
- `ntoskrnl!IoAllocateMdl` at `0x140034906`
- `ntoskrnl!IoBuildPartialMdl` at `0x140034930`
- `ntoskrnl!IoBuildPartialMdl` at `0x140034930`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400349cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400349e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400349cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400349e7`
- `ntoskrnl!ExAllocatePool2` at `0x140034898`
- `ntoskrnl!ExAllocatePool2` at `0x140034898`

## pseudocode

```c

```

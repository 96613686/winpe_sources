# PortPassThroughBuildIrpEx

- ea: `0x14006699c`
- end: `0x140066b7a`
- name: `PortPassThroughBuildIrpEx`
- size: `478`
- prototype: `PIRP __fastcall(__int64, void *, ULONG, char, KPROCESSOR_MODE AccessMode, IRP *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400b8e50`

## callees

- `0x14006699c`
- `0x140067fc0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140066a71`
- `ntoskrnl!IoFreeIrp` at `0x140066b41`
- `ntoskrnl!IoFreeIrp` at `0x140066a71`
- `ntoskrnl!IoFreeIrp` at `0x140066b41`
- `ntoskrnl!IoAllocateMdl` at `0x140066a59`
- `ntoskrnl!IoAllocateMdl` at `0x140066a59`
- `ntoskrnl!IoFreeMdl` at `0x140066b32`
- `ntoskrnl!IoFreeMdl` at `0x140066b32`
- `ntoskrnl!IoAllocateIrp` at `0x1400669fe`
- `ntoskrnl!IoAllocateIrp` at `0x1400669fe`
- `ntoskrnl!MmProbeAndLockPages` at `0x140066ae5`
- `ntoskrnl!MmProbeAndLockPages` at `0x140066ae5`
- `ntoskrnl!IoGetRequestorProcess` at `0x140066a8f`
- `ntoskrnl!IoGetRequestorProcess` at `0x140066a8f`
- `ntoskrnl!IoGetCurrentProcess` at `0x140066aa3`
- `ntoskrnl!IoGetCurrentProcess` at `0x140066aa3`
- `ntoskrnl!KeStackAttachProcess` at `0x140066abc`
- `ntoskrnl!KeStackAttachProcess` at `0x140066abc`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140066afc`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140066b16`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140066afc`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140066b16`

## pseudocode

```c

```

# PortPassThroughBuildIrpEx

- ea: `0x14003d21c`
- end: `0x14003d4f9`
- name: `PortPassThroughBuildIrpEx`
- size: `733`
- prototype: `__int64 __fastcall(int, int, int, int, KPROCESSOR_MODE AccessMode, PIRP, char, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400bcc30`
- `0x1401ba95c`

## callees

- `0x14003d21c`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14003d3cc`
- `ntoskrnl!IoFreeIrp` at `0x14003d45c`
- `ntoskrnl!IoFreeIrp` at `0x14003d3cc`
- `ntoskrnl!IoFreeIrp` at `0x14003d45c`
- `ntoskrnl!IoAllocateMdl` at `0x14003d326`
- `ntoskrnl!IoAllocateMdl` at `0x14003d4b9`
- `ntoskrnl!IoAllocateMdl` at `0x14003d326`
- `ntoskrnl!IoAllocateMdl` at `0x14003d4b9`
- `ntoskrnl!IoFreeMdl` at `0x14003d3bd`
- `ntoskrnl!IoFreeMdl` at `0x14003d44d`
- `ntoskrnl!IoFreeMdl` at `0x1401517bb`
- `ntoskrnl!IoFreeMdl` at `0x14003d3bd`
- `ntoskrnl!IoFreeMdl` at `0x14003d44d`
- `ntoskrnl!IoFreeMdl` at `0x1401517bb`
- `ntoskrnl!IoAllocateIrp` at `0x14003d2c1`
- `ntoskrnl!IoAllocateIrp` at `0x14003d2c1`
- `ntoskrnl!MmUnlockPages` at `0x1401517ab`
- `ntoskrnl!MmUnlockPages` at `0x1401517ab`
- `ntoskrnl!MmProbeAndLockPages` at `0x14003d387`
- `ntoskrnl!MmProbeAndLockPages` at `0x140151752`
- `ntoskrnl!MmProbeAndLockPages` at `0x14003d387`
- `ntoskrnl!MmProbeAndLockPages` at `0x140151752`
- `ntoskrnl!IoGetRequestorProcess` at `0x14003d347`
- `ntoskrnl!IoGetRequestorProcess` at `0x14003d347`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003d35b`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003d35b`
- `ntoskrnl!KeStackAttachProcess` at `0x14003d472`
- `ntoskrnl!KeStackAttachProcess` at `0x14003d4e7`
- `ntoskrnl!KeStackAttachProcess` at `0x14003d472`
- `ntoskrnl!KeStackAttachProcess` at `0x14003d4e7`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14003d3a1`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14003d490`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14015176c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14015178e`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14003d3a1`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14003d490`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14015176c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14015178e`

## pseudocode

```c

```

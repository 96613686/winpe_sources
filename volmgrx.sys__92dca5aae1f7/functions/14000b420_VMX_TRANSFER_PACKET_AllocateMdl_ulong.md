# VMX_TRANSFER_PACKET::AllocateMdl(ulong)

- ea: `0x14000b420`
- end: `0x14000b4d4`
- name: `?AllocateMdl@VMX_TRANSFER_PACKET@@QEAAJK@Z`
- size: `180`
- prototype: `__int64 __fastcall(VMX_TRANSFER_PACKET *this, ULONG)`
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x140008300`
- `0x1400087d0`
- `0x14000de34`
- `0x14000e088`
- `0x14000e2d8`
- `0x14000e464`
- `0x14000e5b4`
- `0x140012244`
- `0x140014fc0`
- `0x140017cd0`
- `0x14004be00`

## callees

- `0x140002b70`
- `0x14000b420`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000b446`
- `ntoskrnl!ExAllocatePool2` at `0x14000b446`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b496`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b496`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000b4b5`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000b4b5`
- `ntoskrnl!IoAllocateMdl` at `0x14000b47c`
- `ntoskrnl!IoAllocateMdl` at `0x14000b47c`

## pseudocode

```c

```

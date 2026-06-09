# VMX_RAID5_WRITE_TRANSFER_PACKET::AllocateMdls(ulong)

- ea: `0x14000b6e8`
- end: `0x14000b7fd`
- name: `?AllocateMdls@VMX_RAID5_WRITE_TRANSFER_PACKET@@QEAAJK@Z`
- size: `277`
- prototype: `__int64 __fastcall(VMX_RAID5_WRITE_TRANSFER_PACKET *__hidden this, ULONG Length)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ea38`
- `0x14004be00`

## callees

- `0x14000b6e8`
- `0x14000d444`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000b708`
- `ntoskrnl!ExAllocatePool2` at `0x14000b782`
- `ntoskrnl!ExAllocatePool2` at `0x14000b708`
- `ntoskrnl!ExAllocatePool2` at `0x14000b782`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b757`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b7d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b757`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b7d4`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000b768`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000b7e5`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000b768`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000b7e5`
- `ntoskrnl!IoAllocateMdl` at `0x14000b73a`
- `ntoskrnl!IoAllocateMdl` at `0x14000b7b7`
- `ntoskrnl!IoAllocateMdl` at `0x14000b73a`
- `ntoskrnl!IoAllocateMdl` at `0x14000b7b7`

## pseudocode

```c

```

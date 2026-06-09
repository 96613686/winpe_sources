# VsmmNumapBackingSetup

- ea: `0x14009c624`
- end: `0x14009c721`
- name: `VsmmNumapBackingSetup`
- size: `253`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14009cf64`

## callees

- `0x140021800`
- `0x14009c624`

## import_xrefs

- `ntoskrnl!MmFreePagesFromMdl` at `0x14009c6ec`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14009c6ec`
- `ntoskrnl!MmUnmapLockedPages` at `0x14009c6c4`
- `ntoskrnl!MmUnmapLockedPages` at `0x14009c6c4`
- `ntoskrnl!MmAllocateNodePagesForMdlEx` at `0x14009c65d`
- `ntoskrnl!MmAllocateNodePagesForMdlEx` at `0x14009c65d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14009c697`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14009c697`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009c702`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009c702`

## pseudocode

```c

```

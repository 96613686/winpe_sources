# VsmmWheapBadPageBitmapSetup

- ea: `0x1400c62ec`
- end: `0x1400c63e6`
- name: `VsmmWheapBadPageBitmapSetup`
- size: `250`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14008279c`

## callees

- `0x14002f524`
- `0x1400c62ec`

## import_xrefs

- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400c6328`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400c6328`
- `ntoskrnl!MmFreePagesFromMdl` at `0x1400c63ac`
- `ntoskrnl!MmFreePagesFromMdl` at `0x1400c63ac`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c6377`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c6377`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c63bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c63bd`

## pseudocode

```c

```

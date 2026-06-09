# VhdmpiCompactionBuildSideFreeList(_VHD1_BACKING_STORE *,_STRUCTURE_BOUNDS *,ulong,ulong,unsigned __int64,_BLOCK_LIST *)

- ea: `0x14009d108`
- end: `0x14009d40e`
- name: `?VhdmpiCompactionBuildSideFreeList@@YAJPEAU_VHD1_BACKING_STORE@@PEAU_STRUCTURE_BOUNDS@@KK_KPEAU_BLOCK_LIST@@@Z`
- size: `774`
- prototype: `__int64 __fastcall(struct _VHD1_BACKING_STORE *, struct _STRUCTURE_BOUNDS *, ULONG, unsigned int, unsigned __int64, struct _BLOCK_LIST *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003c424`

## callees

- `0x140026fa4`
- `0x14009d108`
- `0x14009d414`
- `0x14009d44c`
- `0x1400a05f4`
- `0x1400a0658`
- `0x1400a174c`
- `0x1400e06cc`
- `0x1400e75f4`

## import_xrefs

- `ntoskrnl!RtlInitializeBitMap` at `0x14009d1f9`
- `ntoskrnl!RtlInitializeBitMap` at `0x14009d1f9`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x14009d32a`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x14009d32a`
- `ntoskrnl!RtlSetBits` at `0x14009d26c`
- `ntoskrnl!RtlSetBits` at `0x14009d26c`
- `ntoskrnl!RtlClearAllBits` at `0x14009d23c`
- `ntoskrnl!RtlClearAllBits` at `0x14009d23c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009d1c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009d1c9`
- `ntoskrnl!ExAllocatePool2` at `0x14009d19c`
- `ntoskrnl!ExAllocatePool2` at `0x14009d19c`

## pseudocode

```c

```

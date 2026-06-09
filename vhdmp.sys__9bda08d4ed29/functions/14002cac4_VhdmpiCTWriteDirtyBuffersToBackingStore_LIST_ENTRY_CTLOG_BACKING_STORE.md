# VhdmpiCTWriteDirtyBuffersToBackingStore(_LIST_ENTRY *,_CTLOG_BACKING_STORE *)

- ea: `0x14002cac4`
- end: `0x14002ced4`
- name: `?VhdmpiCTWriteDirtyBuffersToBackingStore@@YAJPEAU_LIST_ENTRY@@PEAU_CTLOG_BACKING_STORE@@@Z`
- size: `1040`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *, struct _CTLOG_BACKING_STORE *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14002c560`

## callees

- `0x1400152fc`
- `0x140023980`
- `0x14002a604`
- `0x14002bfc4`
- `0x14002c1dc`
- `0x14002cac4`
- `0x140036284`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14002cd65`
- `ntoskrnl!IofCallDriver` at `0x14002cd65`
- `ntoskrnl!IoFreeMdl` at `0x14002ccc1`
- `ntoskrnl!IoFreeMdl` at `0x14002cdb1`
- `ntoskrnl!IoFreeMdl` at `0x14002ccc1`
- `ntoskrnl!IoFreeMdl` at `0x14002cdb1`
- `ntoskrnl!IoAllocateMdl` at `0x14002cb9f`
- `ntoskrnl!IoAllocateMdl` at `0x14002cb9f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002cbc6`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002cbc6`

## string_xrefs

- `0x14002ce87`: `VhdmpiCTWriteDirtyBuffersToBackingStore`
- `0x14002ce7b`: `VhdmpiCTWriteDirtyBuffersToBackingStore: ERROR! (backingStore = %p) (VirtualDisk = %p)   Status=0x%x`

## pseudocode

```c

```

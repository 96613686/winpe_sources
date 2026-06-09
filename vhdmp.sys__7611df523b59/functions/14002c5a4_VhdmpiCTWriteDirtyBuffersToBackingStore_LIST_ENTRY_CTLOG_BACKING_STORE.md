# VhdmpiCTWriteDirtyBuffersToBackingStore(_LIST_ENTRY *,_CTLOG_BACKING_STORE *)

- ea: `0x14002c5a4`
- end: `0x14002c9b4`
- name: `?VhdmpiCTWriteDirtyBuffersToBackingStore@@YAJPEAU_LIST_ENTRY@@PEAU_CTLOG_BACKING_STORE@@@Z`
- size: `1040`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *, struct _CTLOG_BACKING_STORE *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14002c040`

## callees

- `0x140014e5c`
- `0x140023560`
- `0x14002a0e4`
- `0x14002baa4`
- `0x14002bcbc`
- `0x14002c5a4`
- `0x140035e94`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14002c845`
- `ntoskrnl!IofCallDriver` at `0x14002c845`
- `ntoskrnl!IoFreeMdl` at `0x14002c7a1`
- `ntoskrnl!IoFreeMdl` at `0x14002c891`
- `ntoskrnl!IoFreeMdl` at `0x14002c7a1`
- `ntoskrnl!IoFreeMdl` at `0x14002c891`
- `ntoskrnl!IoAllocateMdl` at `0x14002c67f`
- `ntoskrnl!IoAllocateMdl` at `0x14002c67f`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002c6a6`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14002c6a6`

## string_xrefs

- `0x14002c95b`: `VhdmpiCTWriteDirtyBuffersToBackingStore: ERROR! (backingStore = %p) (VirtualDisk = %p)   Status=0x%x`
- `0x14002c967`: `VhdmpiCTWriteDirtyBuffersToBackingStore`

## pseudocode

```c

```

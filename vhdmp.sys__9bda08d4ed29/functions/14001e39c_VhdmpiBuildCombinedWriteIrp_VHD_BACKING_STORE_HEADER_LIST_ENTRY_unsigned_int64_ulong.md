# VhdmpiBuildCombinedWriteIrp(_VHD_BACKING_STORE_HEADER *,_LIST_ENTRY *,unsigned __int64,ulong)

- ea: `0x14001e39c`
- end: `0x14001e51c`
- name: `?VhdmpiBuildCombinedWriteIrp@@YAPEAU_IRP@@PEAU_VHD_BACKING_STORE_HEADER@@PEAU_LIST_ENTRY@@_KK@Z`
- size: `384`
- prototype: `struct _IRP *(struct _VHD_BACKING_STORE_HEADER *, struct _LIST_ENTRY *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400dfa70`

## callees

- `0x14001e39c`
- `0x14005de00`

## import_xrefs

- `ntoskrnl!IoAllocateIrpEx` at `0x14001e3cd`
- `ntoskrnl!IoAllocateIrpEx` at `0x14001e3cd`
- `ntoskrnl!IoFreeIrp` at `0x14001e4f8`
- `ntoskrnl!IoFreeIrp` at `0x14001e4f8`
- `ntoskrnl!IoAllocateMdl` at `0x14001e3f9`
- `ntoskrnl!IoAllocateMdl` at `0x14001e3f9`

## pseudocode

```c

```

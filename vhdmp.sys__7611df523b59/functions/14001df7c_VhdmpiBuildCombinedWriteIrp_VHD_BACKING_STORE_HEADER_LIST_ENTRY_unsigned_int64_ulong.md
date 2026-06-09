# VhdmpiBuildCombinedWriteIrp(_VHD_BACKING_STORE_HEADER *,_LIST_ENTRY *,unsigned __int64,ulong)

- ea: `0x14001df7c`
- end: `0x14001e0fc`
- name: `?VhdmpiBuildCombinedWriteIrp@@YAPEAU_IRP@@PEAU_VHD_BACKING_STORE_HEADER@@PEAU_LIST_ENTRY@@_KK@Z`
- size: `384`
- prototype: `struct _IRP *__fastcall(struct _VHD_BACKING_STORE_HEADER *, struct _LIST_ENTRY *, LARGE_INTEGER, ULONG)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400dfae0`

## callees

- `0x14001df7c`
- `0x14005da00`

## import_xrefs

- `ntoskrnl!IoAllocateIrpEx` at `0x14001dfad`
- `ntoskrnl!IoAllocateIrpEx` at `0x14001dfad`
- `ntoskrnl!IoFreeIrp` at `0x14001e0d8`
- `ntoskrnl!IoFreeIrp` at `0x14001e0d8`
- `ntoskrnl!IoAllocateMdl` at `0x14001dfd9`
- `ntoskrnl!IoAllocateMdl` at `0x14001dfd9`

## pseudocode

```c

```

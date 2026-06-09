# VhdmpiOffloadReadOrWriteVhdFileAtPassiveLevel(uchar,_VHD_BACKING_STORE_HEADER *,unsigned __int64,unsigned __int64,unsigned __int64,void *,unsigned __int64 *)

- ea: `0x140032de4`
- end: `0x14003309d`
- name: `?VhdmpiOffloadReadOrWriteVhdFileAtPassiveLevel@@YAJEPEAU_VHD_BACKING_STORE_HEADER@@_K11PEAXPEA_K@Z`
- size: `697`
- prototype: `__int64 __fastcall(unsigned __int8, struct _VHD_BACKING_STORE_HEADER *, unsigned __int64, unsigned __int64, unsigned __int64, void *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14003313c`
- `0x140033170`

## callees

- `0x140012fe0`
- `0x140014710`
- `0x140032de4`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140033076`
- `ntoskrnl!IoFreeIrp` at `0x140033076`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032fcc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032fcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033062`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033062`
- `ntoskrnl!ExAllocatePool2` at `0x140032e47`
- `ntoskrnl!ExAllocatePool2` at `0x140032e47`
- `ntoskrnl!KeInitializeEvent` at `0x140032e27`
- `ntoskrnl!KeInitializeEvent` at `0x140032e27`

## pseudocode

```c

```

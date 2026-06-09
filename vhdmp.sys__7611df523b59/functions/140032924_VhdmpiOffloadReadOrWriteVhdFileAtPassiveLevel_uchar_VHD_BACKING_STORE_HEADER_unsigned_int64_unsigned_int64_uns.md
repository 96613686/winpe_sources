# VhdmpiOffloadReadOrWriteVhdFileAtPassiveLevel(uchar,_VHD_BACKING_STORE_HEADER *,unsigned __int64,unsigned __int64,unsigned __int64,void *,unsigned __int64 *)

- ea: `0x140032924`
- end: `0x140032bdd`
- name: `?VhdmpiOffloadReadOrWriteVhdFileAtPassiveLevel@@YAJEPEAU_VHD_BACKING_STORE_HEADER@@_K11PEAXPEA_K@Z`
- size: `697`
- prototype: `__int64 __fastcall(unsigned __int8, struct _VHD_BACKING_STORE_HEADER *, unsigned __int64, unsigned __int64, unsigned __int64, void *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140032c7c`
- `0x140032cb0`

## callees

- `0x140011cb0`
- `0x140014270`
- `0x140032924`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140032bb6`
- `ntoskrnl!IoFreeIrp` at `0x140032bb6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032b0c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140032b0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032ba2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032ba2`
- `ntoskrnl!ExAllocatePool2` at `0x140032987`
- `ntoskrnl!ExAllocatePool2` at `0x140032987`
- `ntoskrnl!KeInitializeEvent` at `0x140032967`
- `ntoskrnl!KeInitializeEvent` at `0x140032967`

## pseudocode

```c

```

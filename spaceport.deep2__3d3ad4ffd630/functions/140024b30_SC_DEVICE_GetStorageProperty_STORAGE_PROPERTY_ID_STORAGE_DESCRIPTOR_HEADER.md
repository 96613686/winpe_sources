# SC_DEVICE::GetStorageProperty(_STORAGE_PROPERTY_ID,_STORAGE_DESCRIPTOR_HEADER * *)

- ea: `0x140024b30`
- end: `0x140024d2a`
- name: `?GetStorageProperty@SC_DEVICE@@QEAAJW4_STORAGE_PROPERTY_ID@@PEAPEAU_STORAGE_DESCRIPTOR_HEADER@@@Z`
- size: `506`
- prototype: `__int64 __fastcall(SC_DEVICE *__hidden this, enum _STORAGE_PROPERTY_ID, struct _STORAGE_DESCRIPTOR_HEADER **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140026560`

## callees

- `0x140024b30`
- `0x140067fc0`
- `0x140068000`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140024bb4`
- `ntoskrnl!ExAllocatePool2` at `0x140024c1f`
- `ntoskrnl!ExAllocatePool2` at `0x140024bb4`
- `ntoskrnl!ExAllocatePool2` at `0x140024c1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024c88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024cd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024cea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024c88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024cd4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024cea`

## pseudocode

```c

```

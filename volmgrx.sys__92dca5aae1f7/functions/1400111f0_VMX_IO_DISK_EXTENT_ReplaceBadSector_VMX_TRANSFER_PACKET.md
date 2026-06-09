# VMX_IO_DISK_EXTENT::ReplaceBadSector(VMX_TRANSFER_PACKET *)

- ea: `0x1400111f0`
- end: `0x1400113d2`
- name: `?ReplaceBadSector@VMX_IO_DISK_EXTENT@@UEAAXPEAVVMX_TRANSFER_PACKET@@@Z`
- size: `482`
- prototype: `void __fastcall(VMX_IO_DISK_EXTENT *__hidden this, struct VMX_TRANSFER_PACKET *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140004550`
- `0x1400111f0`
- `0x14001b9a0`

## import_xrefs

- `ntoskrnl!ExQueueWorkItem` at `0x1400113b4`
- `ntoskrnl!ExQueueWorkItem` at `0x1400113b4`
- `ntoskrnl!ExAllocatePool2` at `0x1400112a2`
- `ntoskrnl!ExAllocatePool2` at `0x14001134e`
- `ntoskrnl!ExAllocatePool2` at `0x1400112a2`
- `ntoskrnl!ExAllocatePool2` at `0x14001134e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011364`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011364`
- `ntoskrnl!IoFreeIrp` at `0x1400112b9`
- `ntoskrnl!IoFreeIrp` at `0x140011373`
- `ntoskrnl!IoFreeIrp` at `0x1400112b9`
- `ntoskrnl!IoFreeIrp` at `0x140011373`
- `ntoskrnl!IoAllocateIrp` at `0x14001123d`
- `ntoskrnl!IoAllocateIrp` at `0x14001123d`

## pseudocode

```c

```

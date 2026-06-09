# VhdmpiGetFileSecurityDescriptor

- ea: `0x1400bbae4`
- end: `0x1400bbd4e`
- name: `VhdmpiGetFileSecurityDescriptor`
- size: `618`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b9ce4`

## callees

- `0x140023980`
- `0x140036284`
- `0x1400bbae4`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400bbafe`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400bbafe`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400bbb63`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400bbb63`
- `ntoskrnl!IoFreeIrp` at `0x1400bbcb7`
- `ntoskrnl!IoFreeIrp` at `0x1400bbcb7`
- `ntoskrnl!IoFreeMdl` at `0x1400bbc67`
- `ntoskrnl!IoFreeMdl` at `0x1400bbc67`
- `ntoskrnl!MmUnlockPages` at `0x1400bbc47`
- `ntoskrnl!MmUnlockPages` at `0x1400bbc47`
- `ntoskrnl!IoReuseIrp` at `0x1400bbc9e`
- `ntoskrnl!IoReuseIrp` at `0x1400bbc9e`
- `ntoskrnl!IoSynchronousCallDriver` at `0x1400bbc2d`
- `ntoskrnl!IoSynchronousCallDriver` at `0x1400bbc2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbbe1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbcd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbbe1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbcd9`
- `ntoskrnl!ExAllocatePool2` at `0x1400bbbfe`
- `ntoskrnl!ExAllocatePool2` at `0x1400bbbfe`

## string_xrefs

- `0x1400bbb39`: `VhdmpiGetFileSecurityDescriptor: enter...`
- `0x1400bbb4d`: `VhdmpiGetFileSecurityDescriptor`
- `0x1400bbd2e`: `VhdmpiGetFileSecurityDescriptor`

## pseudocode

```c

```

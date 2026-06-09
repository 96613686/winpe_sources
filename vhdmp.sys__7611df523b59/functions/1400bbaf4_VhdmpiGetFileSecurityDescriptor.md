# VhdmpiGetFileSecurityDescriptor

- ea: `0x1400bbaf4`
- end: `0x1400bbd5e`
- name: `VhdmpiGetFileSecurityDescriptor`
- size: `618`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400b9cf4`

## callees

- `0x140023560`
- `0x140035e94`
- `0x1400bbaf4`

## import_xrefs

- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400bbb0e`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400bbb0e`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400bbb73`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400bbb73`
- `ntoskrnl!IoFreeIrp` at `0x1400bbcc7`
- `ntoskrnl!IoFreeIrp` at `0x1400bbcc7`
- `ntoskrnl!IoFreeMdl` at `0x1400bbc77`
- `ntoskrnl!IoFreeMdl` at `0x1400bbc77`
- `ntoskrnl!MmUnlockPages` at `0x1400bbc57`
- `ntoskrnl!MmUnlockPages` at `0x1400bbc57`
- `ntoskrnl!IoReuseIrp` at `0x1400bbcae`
- `ntoskrnl!IoReuseIrp` at `0x1400bbcae`
- `ntoskrnl!IoSynchronousCallDriver` at `0x1400bbc3d`
- `ntoskrnl!IoSynchronousCallDriver` at `0x1400bbc3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbbf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbce9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbbf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bbce9`
- `ntoskrnl!ExAllocatePool2` at `0x1400bbc0e`
- `ntoskrnl!ExAllocatePool2` at `0x1400bbc0e`

## string_xrefs

- `0x1400bbb49`: `VhdmpiGetFileSecurityDescriptor: enter...`
- `0x1400bbb5d`: `VhdmpiGetFileSecurityDescriptor`
- `0x1400bbd3e`: `VhdmpiGetFileSecurityDescriptor`

## pseudocode

```c

```

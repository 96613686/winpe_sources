# Smb2RkfFsctl

- ea: `0x14006e6d0`
- end: `0x14006e9e2`
- name: `Smb2RkfFsctl`
- size: `786`
- prototype: `__int64 __fastcall(__int64, struct _FILE_OBJECT *, struct _NAMED_PIPE_CREATE_PARAMETERS *, ULONG, void *, ULONG, _DWORD *)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x14000cdf0`
- `0x14006d158`
- `0x14006dd70`
- `0x14006e650`
- `0x14006e9e8`
- `0x14006ea80`
- `0x14006eb18`
- `0x14006ed0c`
- `0x140082290`

## callees

- `0x14002019c`
- `0x1400224b8`
- `0x1400341b4`
- `0x14006e6d0`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14006e8c0`
- `ntoskrnl!IoFreeMdl` at `0x14006e8c0`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006e78a`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x14006e78a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006e859`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006e859`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006e6fb`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006e6fb`
- `ntoskrnl!IofCallDriver` at `0x14006e82e`
- `ntoskrnl!IofCallDriver` at `0x14006e82e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e876`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e876`
- `ntoskrnl!IoFreeIrp` at `0x14006e9c6`
- `ntoskrnl!IoFreeIrp` at `0x14006e9c6`
- `ntoskrnl!IoAllocateIrpEx` at `0x14006e713`
- `ntoskrnl!IoAllocateIrpEx` at `0x14006e713`
- `ntoskrnl!KeInitializeEvent` at `0x14006e770`
- `ntoskrnl!KeInitializeEvent` at `0x14006e770`
- `ntoskrnl!MmUnlockPages` at `0x14006e8b1`
- `ntoskrnl!MmUnlockPages` at `0x14006e8b1`

## pseudocode

```c

```

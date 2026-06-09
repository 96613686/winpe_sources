# VmsIovAllocateMacFiltersForNic

- ea: `0x14012e294`
- end: `0x14012ebfc`
- name: `VmsIovAllocateMacFiltersForNic`
- size: `2408`
- prototype: ``
- caller_count: `6`
- callee_count: `21`
- tags: `installer_update`

## callers

- `0x140088c50`
- `0x14008cc04`
- `0x14012c0e0`
- `0x14012ec04`
- `0x1401321d8`
- `0x140132438`

## callees

- `0x140014988`
- `0x140027a64`
- `0x14002e0f0`
- `0x140035438`
- `0x14003a450`
- `0x14003e9e4`
- `0x14004f5d8`
- `0x14008497c`
- `0x1400893c8`
- `0x1400953e8`
- `0x1400e00d0`
- `0x1400e056c`
- `0x14012e294`
- `0x140131f08`
- `0x140132ec0`
- `0x140135ef8`
- `0x14014a1e4`
- `0x14015c020`
- `0x14019283c`
- `0x1401bbcb0`
- `0x1401bc340`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14012e7a5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14012e7a5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14012e746`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14012e746`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012e3aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012e3aa`
- `ntoskrnl!ExAllocatePool2` at `0x14012e6f6`
- `ntoskrnl!ExAllocatePool2` at `0x14012e7bd`
- `ntoskrnl!ExAllocatePool2` at `0x14012e8ae`
- `ntoskrnl!ExAllocatePool2` at `0x14012e6f6`
- `ntoskrnl!ExAllocatePool2` at `0x14012e7bd`
- `ntoskrnl!ExAllocatePool2` at `0x14012e8ae`

## string_xrefs

- `0x14012e48c`: `nicPort->VlanInfo.OperationMode == VmsVlanModeAccess`
- `0x14012e4cf`: `nicPort->VlanInfo.AccessVlanId == 0`

## pseudocode

```c

```

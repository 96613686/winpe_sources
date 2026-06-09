# VmsIovAllocateMacFiltersForNic

- ea: `0x14012e224`
- end: `0x14012eb8c`
- name: `VmsIovAllocateMacFiltersForNic`
- size: `2408`
- prototype: ``
- caller_count: `6`
- callee_count: `21`
- tags: `installer_update`

## callers

- `0x140088c50`
- `0x14008cc04`
- `0x14012c070`
- `0x14012eb94`
- `0x140132168`
- `0x1401323c8`

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
- `0x1400e0060`
- `0x1400e04fc`
- `0x14012e224`
- `0x140131e98`
- `0x140132e50`
- `0x140135e88`
- `0x14014a174`
- `0x14015bfb0`
- `0x1401927cc`
- `0x1401bbc40`
- `0x1401bc2c0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14012e735`
- `ntoskrnl!KeReleaseSpinLock` at `0x14012e735`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14012e6d6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14012e6d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012e33a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012e33a`
- `ntoskrnl!ExAllocatePool2` at `0x14012e686`
- `ntoskrnl!ExAllocatePool2` at `0x14012e74d`
- `ntoskrnl!ExAllocatePool2` at `0x14012e83e`
- `ntoskrnl!ExAllocatePool2` at `0x14012e686`
- `ntoskrnl!ExAllocatePool2` at `0x14012e74d`
- `ntoskrnl!ExAllocatePool2` at `0x14012e83e`

## string_xrefs

- `0x14012e45f`: `nicPort->VlanInfo.AccessVlanId == 0`
- `0x14012e41c`: `nicPort->VlanInfo.OperationMode == VmsVlanModeAccess`

## pseudocode

```c

```

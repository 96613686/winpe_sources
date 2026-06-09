# VmsOmPortSetRequiredExtensions

- ea: `0x14010d650`
- end: `0x14010d7d8`
- name: `VmsOmPortSetRequiredExtensions`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400d0ddc`

## callees

- `0x14002e0f0`
- `0x140046f1c`
- `0x14006b084`
- `0x140078a50`
- `0x14010d650`
- `0x1401bc040`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14010d78a`
- `ntoskrnl!KeReleaseMutex` at `0x14010d78a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010d759`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010d759`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010d708`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010d708`
- `ntoskrnl!ExAllocatePool2` at `0x14010d691`
- `ntoskrnl!ExAllocatePool2` at `0x14010d691`
- `NDIS!NdisReleaseRWLock` at `0x14010d735`
- `NDIS!NdisReleaseRWLock` at `0x1401bcfa0`
- `NDIS!NdisReleaseRWLock` at `0x14010d735`
- `NDIS!NdisReleaseRWLock` at `0x1401bcfa0`

## pseudocode

```c

```

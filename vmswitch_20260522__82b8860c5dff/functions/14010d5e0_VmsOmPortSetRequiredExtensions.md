# VmsOmPortSetRequiredExtensions

- ea: `0x14010d5e0`
- end: `0x14010d768`
- name: `VmsOmPortSetRequiredExtensions`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400d0d6c`

## callees

- `0x14002e0f0`
- `0x140046f1c`
- `0x14006b084`
- `0x140078a50`
- `0x14010d5e0`
- `0x1401bbfc0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14010d71a`
- `ntoskrnl!KeReleaseMutex` at `0x14010d71a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010d6e9`
- `ntoskrnl!KeWaitForSingleObject` at `0x14010d6e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010d698`
- `ntoskrnl!ExFreePoolWithTag` at `0x14010d698`
- `ntoskrnl!ExAllocatePool2` at `0x14010d621`
- `ntoskrnl!ExAllocatePool2` at `0x14010d621`
- `NDIS!NdisReleaseRWLock` at `0x14010d6c5`
- `NDIS!NdisReleaseRWLock` at `0x1401bcf20`
- `NDIS!NdisReleaseRWLock` at `0x14010d6c5`
- `NDIS!NdisReleaseRWLock` at `0x1401bcf20`

## pseudocode

```c

```

# StorpAdapterTopologyWorkItemRoutine

- ea: `0x140046870`
- end: `0x140046a2d`
- name: `StorpAdapterTopologyWorkItemRoutine`
- size: `445`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400290b0`
- `0x140046870`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x140046a1c`
- `ntoskrnl!IoFreeWorkItem` at `0x140046a1c`
- `ntoskrnl!IofCallDriver` at `0x1400469c2`
- `ntoskrnl!IofCallDriver` at `0x1400469c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046a08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140152d3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140046a08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140152d3c`
- `ntoskrnl!KeInitializeEvent` at `0x1400468eb`
- `ntoskrnl!KeInitializeEvent` at `0x1400468eb`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400469ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400469ee`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14004691c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14004691c`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14004699f`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x14004699f`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400468c3`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400468c3`

## pseudocode

```c

```

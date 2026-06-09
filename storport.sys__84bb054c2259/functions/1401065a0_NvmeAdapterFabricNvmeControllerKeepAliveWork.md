# NvmeAdapterFabricNvmeControllerKeepAliveWork

- ea: `0x1401065a0`
- end: `0x140106928`
- name: `NvmeAdapterFabricNvmeControllerKeepAliveWork`
- size: `904`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14005285c`
- `0x1400b71f8`
- `0x1401065a0`
- `0x140109878`
- `0x140116f08`

## import_xrefs

- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1401065f6`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1401065f6`
- `ntoskrnl!KeSetEvent` at `0x140106854`
- `ntoskrnl!KeSetEvent` at `0x140106854`
- `ntoskrnl!KeCancelTimer` at `0x1401067d5`
- `ntoskrnl!KeCancelTimer` at `0x1401067d5`
- `ntoskrnl!IoQueueWorkItem` at `0x14010683c`
- `ntoskrnl!IoQueueWorkItem` at `0x14010683c`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140106917`
- `ntoskrnl!KeSetCoalescableTimer` at `0x140106917`
- `ntoskrnl!KeClearEvent` at `0x14010681c`
- `ntoskrnl!KeClearEvent` at `0x1401068eb`
- `ntoskrnl!KeClearEvent` at `0x14010681c`
- `ntoskrnl!KeClearEvent` at `0x1401068eb`
- `ntoskrnl!KeRemoveQueueDpc` at `0x1401067f0`
- `ntoskrnl!KeRemoveQueueDpc` at `0x1401067f0`
- `HAL!KeQueryPerformanceCounter` at `0x1401065e8`
- `HAL!KeQueryPerformanceCounter` at `0x1401065e8`

## pseudocode

```c

```

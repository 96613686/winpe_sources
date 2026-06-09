# NvmeControllerInitializeCompletionQueueDPC

- ea: `0x140111f14`
- end: `0x1401120d9`
- name: `NvmeControllerInitializeCompletionQueueDPC`
- size: `453`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140111a34`
- `0x140112d20`

## callees

- `0x1400290b0`
- `0x140111f14`

## import_xrefs

- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x14011206b`
- `ntoskrnl!KeSetTargetProcessorDpcEx` at `0x14011206b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140111f48`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401120b1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140111f48`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401120b1`
- `ntoskrnl!KeGetProcessorIndexFromNumber` at `0x14011201b`
- `ntoskrnl!KeGetProcessorIndexFromNumber` at `0x14011201b`
- `ntoskrnl!KeInitializeDpc` at `0x14011203b`
- `ntoskrnl!KeInitializeDpc` at `0x14011203b`
- `ntoskrnl!KeSetImportanceDpc` at `0x140112053`
- `ntoskrnl!KeSetImportanceDpc` at `0x140112053`

## pseudocode

```c

```

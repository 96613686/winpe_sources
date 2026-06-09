# IppDeferNetworkStateUpdateProcessing

- ea: `0x1400993a0`
- end: `0x14009955c`
- name: `IppDeferNetworkStateUpdateProcessing`
- size: `444`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14008a410`
- `0x140099bec`
- `0x140119aec`
- `0x140124a10`
- `0x140159ea0`
- `0x14018cfa0`
- `0x14018d360`

## callees

- `0x140014a08`
- `0x1400993a0`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x1400994d9`
- `ntoskrnl!IoQueueWorkItem` at `0x1400994d9`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400993e3`
- `ntoskrnl!IoAllocateWorkItem` at `0x1400993e3`
- `ntoskrnl!IoFreeWorkItem` at `0x140099420`
- `ntoskrnl!IoFreeWorkItem` at `0x1400994fb`
- `ntoskrnl!IoFreeWorkItem` at `0x140099420`
- `ntoskrnl!IoFreeWorkItem` at `0x1400994fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140099431`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400994ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009950c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140099537`
- `ntoskrnl!ExFreePoolWithTag` at `0x140099431`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400994ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009950c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140099537`
- `ntoskrnl!ExAllocatePool2` at `0x1400993c4`
- `ntoskrnl!ExAllocatePool2` at `0x140099409`
- `ntoskrnl!ExAllocatePool2` at `0x1400993c4`
- `ntoskrnl!ExAllocatePool2` at `0x140099409`

## string_xrefs

- `0x140099550`: `network state update work queue item (IPNG)`
- `0x140099526`: `network state update workitem (IPNG)`
- `0x140099446`: `network state update operation (IPNG)`

## pseudocode

```c

```

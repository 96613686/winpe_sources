# IppDeferNetworkStateUpdateProcessing

- ea: `0x140045454`
- end: `0x140045610`
- name: `IppDeferNetworkStateUpdateProcessing`
- size: `444`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140043a10`
- `0x140045ff4`
- `0x14010fa7c`
- `0x14011a790`
- `0x140157fd0`
- `0x14018b330`
- `0x14018b6f0`

## callees

- `0x140045454`
- `0x140053e98`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14004558d`
- `ntoskrnl!IoQueueWorkItem` at `0x14004558d`
- `ntoskrnl!IoAllocateWorkItem` at `0x140045497`
- `ntoskrnl!IoAllocateWorkItem` at `0x140045497`
- `ntoskrnl!IoFreeWorkItem` at `0x1400454d4`
- `ntoskrnl!IoFreeWorkItem` at `0x1400455af`
- `ntoskrnl!IoFreeWorkItem` at `0x1400454d4`
- `ntoskrnl!IoFreeWorkItem` at `0x1400455af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400454e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400455a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400455c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400455eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400454e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400455a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400455c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400455eb`
- `ntoskrnl!ExAllocatePool2` at `0x140045478`
- `ntoskrnl!ExAllocatePool2` at `0x1400454bd`
- `ntoskrnl!ExAllocatePool2` at `0x140045478`
- `ntoskrnl!ExAllocatePool2` at `0x1400454bd`

## string_xrefs

- `0x1400455da`: `network state update workitem (IPNG)`
- `0x140045604`: `network state update work queue item (IPNG)`
- `0x1400454fa`: `network state update operation (IPNG)`

## pseudocode

```c

```

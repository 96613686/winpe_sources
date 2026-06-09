# IppDeferNetworkStateUpdateProcessing

- ea: `0x1400456f4`
- end: `0x1400458b0`
- name: `IppDeferNetworkStateUpdateProcessing`
- size: `444`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140043cb0`
- `0x140046294`
- `0x14010fbbc`
- `0x14011a8d0`
- `0x140158110`
- `0x14018b470`
- `0x14018b830`

## callees

- `0x1400456f4`
- `0x140054138`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x14004582d`
- `ntoskrnl!IoQueueWorkItem` at `0x14004582d`
- `ntoskrnl!IoAllocateWorkItem` at `0x140045737`
- `ntoskrnl!IoAllocateWorkItem` at `0x140045737`
- `ntoskrnl!IoFreeWorkItem` at `0x140045774`
- `ntoskrnl!IoFreeWorkItem` at `0x14004584f`
- `ntoskrnl!IoFreeWorkItem` at `0x140045774`
- `ntoskrnl!IoFreeWorkItem` at `0x14004584f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045785`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045840`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045860`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004588b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045785`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045840`
- `ntoskrnl!ExFreePoolWithTag` at `0x140045860`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004588b`
- `ntoskrnl!ExAllocatePool2` at `0x140045718`
- `ntoskrnl!ExAllocatePool2` at `0x14004575d`
- `ntoskrnl!ExAllocatePool2` at `0x140045718`
- `ntoskrnl!ExAllocatePool2` at `0x14004575d`

## string_xrefs

- `0x14004579a`: `network state update operation (IPNG)`
- `0x1400458a4`: `network state update work queue item (IPNG)`
- `0x14004587a`: `network state update workitem (IPNG)`

## pseudocode

```c

```

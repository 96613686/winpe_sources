# NvmeControllerProcessPendingCommand

- ea: `0x14003e8b0`
- end: `0x14003ea8a`
- name: `NvmeControllerProcessPendingCommand`
- size: `474`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14003e1a0`
- `0x14003e840`
- `0x140045920`
- `0x14005ed70`
- `0x1401348c0`

## callees

- `0x14003e8b0`
- `0x14003ea90`
- `0x140062cc0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14015199a`
- `ntoskrnl!KeSetEvent` at `0x14015199a`
- `ntoskrnl!KeLowerIrql` at `0x14003e959`
- `ntoskrnl!KeLowerIrql` at `0x14003e9bf`
- `ntoskrnl!KeLowerIrql` at `0x14003e959`
- `ntoskrnl!KeLowerIrql` at `0x14003e9bf`
- `ntoskrnl!KfRaiseIrql` at `0x14003e926`
- `ntoskrnl!KfRaiseIrql` at `0x14003e926`
- `ntoskrnl!IoQueueWorkItem` at `0x1401519bd`
- `ntoskrnl!IoQueueWorkItem` at `0x1401519bd`
- `ntoskrnl!ExQueryDepthSList` at `0x1401518ff`
- `ntoskrnl!ExQueryDepthSList` at `0x1401518ff`

## pseudocode

```c

```

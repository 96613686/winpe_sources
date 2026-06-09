# NvmeAdapterFabricsAddAuthenticationKeyIoctl

- ea: `0x1401a1098`
- end: `0x1401a1526`
- name: `NvmeAdapterFabricsAddAuthenticationKeyIoctl`
- size: `1166`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1401a0208`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x140099750`
- `0x14009a084`
- `0x140102adc`
- `0x14014b400`
- `0x14014b800`
- `0x1401a1098`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a117f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a117f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a1195`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a1195`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a124d`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a124d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a1200`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a1200`
- `ntoskrnl!IofCompleteRequest` at `0x1401a14f6`
- `ntoskrnl!IofCompleteRequest` at `0x1401a14f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a120c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a120c`

## pseudocode

```c

```

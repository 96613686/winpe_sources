# NvmeAdapterFabricsCreateAuthenticationKeyIoctl

- ea: `0x1401a2b28`
- end: `0x1401a3081`
- name: `NvmeAdapterFabricsCreateAuthenticationKeyIoctl`
- size: `1369`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1401a0208`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x140099750`
- `0x14009992c`
- `0x14009a084`
- `0x1400b1ff8`
- `0x140102adc`
- `0x14014b400`
- `0x14014b800`
- `0x1401a2b28`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a2d2e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a2d2e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a2d44`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a2d44`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a2c76`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a2c76`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a2dae`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a2dae`
- `ntoskrnl!IofCompleteRequest` at `0x1401a304f`
- `ntoskrnl!IofCompleteRequest` at `0x1401a304f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a2dba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a2dba`

## pseudocode

```c

```

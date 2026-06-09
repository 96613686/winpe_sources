# NvmeAdapterFabricsDeleteAuthenticationKeyIoctl

- ea: `0x1401a3088`
- end: `0x1401a34a5`
- name: `NvmeAdapterFabricsDeleteAuthenticationKeyIoctl`
- size: `1053`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1401a0208`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x14009a084`
- `0x14009b9b0`
- `0x14014b400`
- `0x1401a3088`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a313f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a313f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a3155`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1401a3155`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a31ca`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a31ca`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a317d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a317d`
- `ntoskrnl!IofCompleteRequest` at `0x1401a3475`
- `ntoskrnl!IofCompleteRequest` at `0x1401a3475`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a3189`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a3189`

## pseudocode

```c

```

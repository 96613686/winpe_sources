# NvmeAdapterFabricsGetAuthenticationKeysIoctl

- ea: `0x1401a3a0c`
- end: `0x1401a3fbf`
- name: `NvmeAdapterFabricsGetAuthenticationKeysIoctl`
- size: `1459`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1401a0208`

## callees

- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x14009a084`
- `0x140102adc`
- `0x14014b400`
- `0x14014b800`
- `0x1401a3a0c`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a3ba6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401a3ba6`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a3cda`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1401a3cda`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a3c7e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1401a3c7e`
- `ntoskrnl!IofCompleteRequest` at `0x1401a3f8d`
- `ntoskrnl!IofCompleteRequest` at `0x1401a3f8d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a3c8a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1401a3c8a`
- `ntoskrnl!_strnicmp` at `0x1401a3c07`
- `ntoskrnl!_strnicmp` at `0x1401a3c07`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplaying` at `0x1401a3bd4`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplaying` at `0x1401a3c5a`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplaying` at `0x1401a3bd4`
- `ntoskrnl!RtlEnumerateGenericTableWithoutSplaying` at `0x1401a3c5a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a3bbc`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1401a3bbc`

## pseudocode

```c

```

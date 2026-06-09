# VmsVmNicPvtDestroySendBuffers

- ea: `0x14006ae30`
- end: `0x14006b07e`
- name: `VmsVmNicPvtDestroySendBuffers`
- size: `590`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140090334`
- `0x14019d2e0`

## callees

- `0x140027a64`
- `0x14006ae30`
- `0x14008497c`

## import_xrefs

- `ntoskrnl!MmFreePagesFromMdl` at `0x14006b02d`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14006b02d`
- `ntoskrnl!IoFreeMdl` at `0x14006aecd`
- `ntoskrnl!IoFreeMdl` at `0x14006af02`
- `ntoskrnl!IoFreeMdl` at `0x14006aecd`
- `ntoskrnl!IoFreeMdl` at `0x14006af02`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006af2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b042`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b066`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006af2f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b042`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006b066`
- `NDIS!NdisReleaseRWLock` at `0x14006af9d`
- `NDIS!NdisReleaseRWLock` at `0x14006af9d`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006ae78`
- `NDIS!NdisAcquireRWLockWrite` at `0x14006ae78`
- `vmbkmclr!VmbChannelUnmapGpadl` at `0x14006af81`
- `vmbkmclr!VmbChannelUnmapGpadl` at `0x14006af81`

## pseudocode

```c

```

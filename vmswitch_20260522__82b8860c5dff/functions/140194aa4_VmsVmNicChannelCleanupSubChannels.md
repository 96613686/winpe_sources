# VmsVmNicChannelCleanupSubChannels

- ea: `0x140194aa4`
- end: `0x140194c44`
- name: `VmsVmNicChannelCleanupSubChannels`
- size: `416`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140090334`

## callees

- `0x14000bc0c`
- `0x140027a64`
- `0x14006b084`
- `0x1400844bc`
- `0x14008497c`
- `0x1400849b0`
- `0x140194aa4`
- `0x140194c4c`
- `0x1401af578`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140194c2e`
- `ntoskrnl!KeReleaseMutex` at `0x140194c2e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140194bf9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140194bf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140194bd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140194bd0`
- `NDIS!NdisReleaseRWLock` at `0x140194b36`
- `NDIS!NdisReleaseRWLock` at `0x140194ba0`
- `NDIS!NdisReleaseRWLock` at `0x140194b36`
- `NDIS!NdisReleaseRWLock` at `0x140194ba0`

## string_xrefs

- `0x140194ace`: `ChannelState->IsAllocated && ChannelState->IsOpened == 0`

## pseudocode

```c

```

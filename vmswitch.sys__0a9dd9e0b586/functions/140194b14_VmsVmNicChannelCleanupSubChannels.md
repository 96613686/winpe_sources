# VmsVmNicChannelCleanupSubChannels

- ea: `0x140194b14`
- end: `0x140194cb4`
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
- `0x140194b14`
- `0x140194cbc`
- `0x1401af5e8`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140194c9e`
- `ntoskrnl!KeReleaseMutex` at `0x140194c9e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140194c69`
- `ntoskrnl!KeWaitForSingleObject` at `0x140194c69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140194c40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140194c40`
- `NDIS!NdisReleaseRWLock` at `0x140194ba6`
- `NDIS!NdisReleaseRWLock` at `0x140194c10`
- `NDIS!NdisReleaseRWLock` at `0x140194ba6`
- `NDIS!NdisReleaseRWLock` at `0x140194c10`

## string_xrefs

- `0x140194b3e`: `ChannelState->IsAllocated && ChannelState->IsOpened == 0`

## pseudocode

```c

```

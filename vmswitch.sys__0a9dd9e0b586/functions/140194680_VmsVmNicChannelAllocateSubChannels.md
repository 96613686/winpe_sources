# VmsVmNicChannelAllocateSubChannels

- ea: `0x140194680`
- end: `0x140194b0c`
- name: `VmsVmNicChannelAllocateSubChannels`
- size: `1164`
- prototype: `__int64 __fastcall(__int64 *, unsigned int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x14019cd00`
- `0x14019f780`

## callees

- `0x140027a64`
- `0x14003a450`
- `0x14003e804`
- `0x140046f1c`
- `0x14004a1b4`
- `0x140051528`
- `0x14006b084`
- `0x14007a890`
- `0x140083834`
- `0x14008497c`
- `0x1400867a0`
- `0x14012c710`
- `0x140194188`
- `0x140194680`
- `0x140194cbc`
- `0x1401a8a80`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtection` at `0x14019480f`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14019480f`
- `ntoskrnl!KeReleaseMutex` at `0x140194ac5`
- `ntoskrnl!KeReleaseMutex` at `0x140194ac5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140194a6e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140194a6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401948f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401948f0`
- `ntoskrnl!ExAllocatePool2` at `0x140194735`
- `ntoskrnl!ExAllocatePool2` at `0x140194735`
- `NDIS!NdisReleaseRWLock` at `0x140194a4e`
- `NDIS!NdisReleaseRWLock` at `0x140194a4e`
- `vmbkmclr!VmbChannelEnable` at `0x1401947d8`
- `vmbkmclr!VmbChannelEnable` at `0x1401947d8`

## string_xrefs

- `0x140194ae2`: `!"The VMNic already has subchannels allocated."`

## pseudocode

```c

```

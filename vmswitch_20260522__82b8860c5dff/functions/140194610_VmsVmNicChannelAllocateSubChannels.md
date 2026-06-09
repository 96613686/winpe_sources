# VmsVmNicChannelAllocateSubChannels

- ea: `0x140194610`
- end: `0x140194a9c`
- name: `VmsVmNicChannelAllocateSubChannels`
- size: `1164`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x14019cc90`
- `0x14019f710`

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
- `0x14012c6a0`
- `0x140194118`
- `0x140194610`
- `0x140194c4c`
- `0x1401a8a10`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtection` at `0x14019479f`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14019479f`
- `ntoskrnl!KeReleaseMutex` at `0x140194a55`
- `ntoskrnl!KeReleaseMutex` at `0x140194a55`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401949fe`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401949fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140194880`
- `ntoskrnl!ExFreePoolWithTag` at `0x140194880`
- `ntoskrnl!ExAllocatePool2` at `0x1401946c5`
- `ntoskrnl!ExAllocatePool2` at `0x1401946c5`
- `NDIS!NdisReleaseRWLock` at `0x1401949de`
- `NDIS!NdisReleaseRWLock` at `0x1401949de`
- `vmbkmclr!VmbChannelEnable` at `0x140194768`
- `vmbkmclr!VmbChannelEnable` at `0x140194768`

## string_xrefs

- `0x140194a72`: `!"The VMNic already has subchannels allocated."`

## pseudocode

```c

```

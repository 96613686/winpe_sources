# WfpAleAuthorizeConnect

- ea: `0x1400cd0b0`
- end: `0x1400cdfa8`
- name: `WfpAleAuthorizeConnect`
- size: `3832`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int16, __int64, int, __int64, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: ``

## callers

- `0x1400ccbb0`

## callees

- `0x140014c50`
- `0x140014dd0`
- `0x14002bb30`
- `0x14004bf80`
- `0x1400507f8`
- `0x140052390`
- `0x140053f20`
- `0x140054f00`
- `0x140055780`
- `0x14008a370`
- `0x14008dec0`
- `0x14008e020`
- `0x1400ac790`
- `0x1400b2b10`
- `0x1400cd0b0`
- `0x1400e3ec0`
- `0x1400fd434`
- `0x14011ca58`
- `0x140137d00`
- `0x14013c160`
- `0x1401502cc`
- `0x140150a10`
- `0x140170e1c`
- `0x1401bf390`
- `0x1401bf640`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x1400cdf04`
- `ntoskrnl!IoQueueWorkItem` at `0x1400cdf04`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400cdd25`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400cdd25`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400cddba`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400cddba`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400cd185`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400cd185`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd68f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cddd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cdf2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cdf45`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd68f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cddd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cdf2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cdf45`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd2bf`
- `ntoskrnl!ExAllocatePool2` at `0x1400cdb8b`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd2bf`
- `ntoskrnl!ExAllocatePool2` at `0x1400cdb8b`
- `NETIO!KfdIsLayerEmpty` at `0x1400cd3a3`
- `NETIO!KfdIsLayerEmpty` at `0x1400cd42a`
- `NETIO!KfdIsLayerEmpty` at `0x1400cd3a3`
- `NETIO!KfdIsLayerEmpty` at `0x1400cd42a`
- `NETIO!KfdCheckConnectBypass` at `0x1400cd62d`
- `NETIO!KfdCheckConnectBypass` at `0x1400cd62d`
- `NETIO!NetioNrtReferenceRecord` at `0x1400cd26d`
- `NETIO!NetioNrtReferenceRecord` at `0x1400cd26d`

## string_xrefs

- `0x1400cdc53`: `WfpAleQueryPeerTokenInformation`
- `0x1400cdcfb`: `WfpStringCchCopyA`
- `0x1400cdcb9`: `StringCchCopyA`

## pseudocode

```c

```

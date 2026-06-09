# WfpAleAuthorizeConnect

- ea: `0x1400cce90`
- end: `0x1400cdd88`
- name: `WfpAleAuthorizeConnect`
- size: `3832`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int16, __int64, int, __int64, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: ``

## callers

- `0x1400cc990`

## callees

- `0x140014c50`
- `0x140014dd0`
- `0x14002bdd0`
- `0x14004c220`
- `0x140050a98`
- `0x140052630`
- `0x1400541c0`
- `0x1400551a0`
- `0x140055a20`
- `0x14008b220`
- `0x14008ed70`
- `0x14008eed0`
- `0x1400b2730`
- `0x1400cce90`
- `0x1400e3ca0`
- `0x1400fd574`
- `0x14010bb80`
- `0x14011cb98`
- `0x140137e90`
- `0x14013c2f0`
- `0x14015040c`
- `0x140150b50`
- `0x140170f5c`
- `0x1401bf4d0`
- `0x1401bf780`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x1400cdce4`
- `ntoskrnl!IoQueueWorkItem` at `0x1400cdce4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400cdb05`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400cdb05`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400cdb9a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400cdb9a`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400ccf65`
- `ntoskrnl!KeQueryInterruptTimePrecise` at `0x1400ccf65`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd46f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cdbb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cdd0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cdd25`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd46f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cdbb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cdd0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cdd25`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd09f`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd96b`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd09f`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd96b`
- `NETIO!KfdIsLayerEmpty` at `0x1400cd183`
- `NETIO!KfdIsLayerEmpty` at `0x1400cd20a`
- `NETIO!KfdIsLayerEmpty` at `0x1400cd183`
- `NETIO!KfdIsLayerEmpty` at `0x1400cd20a`
- `NETIO!KfdCheckConnectBypass` at `0x1400cd40d`
- `NETIO!KfdCheckConnectBypass` at `0x1400cd40d`
- `NETIO!NetioNrtReferenceRecord` at `0x1400cd04d`
- `NETIO!NetioNrtReferenceRecord` at `0x1400cd04d`

## string_xrefs

- `0x1400cda33`: `WfpAleQueryPeerTokenInformation`
- `0x1400cda99`: `StringCchCopyA`
- `0x1400cdadb`: `WfpStringCchCopyA`

## pseudocode

```c

```

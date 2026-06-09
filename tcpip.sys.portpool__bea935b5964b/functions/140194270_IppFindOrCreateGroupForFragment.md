# IppFindOrCreateGroupForFragment

- ea: `0x140194270`
- end: `0x140194675`
- name: `IppFindOrCreateGroupForFragment`
- size: `1029`
- prototype: `__int64 __fastcall(__int64, struct _LIST_ENTRY *, __int64, __int64, void *Src, void *, unsigned int, int, char, __int64 *, KIRQL *, _DWORD *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400f8430`
- `0x1400ff954`

## callees

- `0x140014a08`
- `0x140063db0`
- `0x1400911b0`
- `0x1400f1f80`
- `0x1400f25e8`
- `0x140194270`
- `0x1401c1280`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14019437c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140194622`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14019437c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140194622`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140194396`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140194631`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140194396`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140194631`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1401943b2`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1401943b2`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14019431d`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14019431d`
- `ntoskrnl!ExAllocatePool3` at `0x1401943ed`
- `ntoskrnl!ExAllocatePool3` at `0x1401943ed`
- `ntoskrnl!KeReleaseSpinLock` at `0x140194407`
- `ntoskrnl!KeReleaseSpinLock` at `0x140194501`
- `ntoskrnl!KeReleaseSpinLock` at `0x140194407`
- `ntoskrnl!KeReleaseSpinLock` at `0x140194501`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019442f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019442f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401942cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401942cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140194512`
- `ntoskrnl!ExFreePoolWithTag` at `0x140194512`
- `NETIO!NetioFreeNetBufferAndNetBufferList` at `0x1401944ef`
- `NETIO!NetioFreeNetBufferAndNetBufferList` at `0x1401944ef`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x1401944bd`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x1401944bd`
- `fwpkclnt!FwppvSwitchCopyVmSwitchNblInfo` at `0x1401944da`
- `fwpkclnt!FwppvSwitchCopyVmSwitchNblInfo` at `0x1401944da`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14019456a`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14019456a`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x140194497`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x140194497`

## pseudocode

```c

```

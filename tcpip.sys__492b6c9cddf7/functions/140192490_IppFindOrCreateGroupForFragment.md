# IppFindOrCreateGroupForFragment

- ea: `0x140192490`
- end: `0x140192895`
- name: `IppFindOrCreateGroupForFragment`
- size: `1029`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, void *, int, int, char, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400f1bc0`
- `0x1400f78b4`

## callees

- `0x140053e98`
- `0x140077970`
- `0x1400a8030`
- `0x1400eac80`
- `0x1400eb2e8`
- `0x140192490`
- `0x1401bf640`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14019259c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140192842`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14019259c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140192842`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401925b6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140192851`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1401925b6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140192851`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1401925d2`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x1401925d2`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14019253d`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14019253d`
- `ntoskrnl!ExAllocatePool3` at `0x14019260d`
- `ntoskrnl!ExAllocatePool3` at `0x14019260d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140192627`
- `ntoskrnl!KeReleaseSpinLock` at `0x140192721`
- `ntoskrnl!KeReleaseSpinLock` at `0x140192627`
- `ntoskrnl!KeReleaseSpinLock` at `0x140192721`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019264f`
- `ntoskrnl!KeInitializeSpinLock` at `0x14019264f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401924ec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1401924ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192732`
- `ntoskrnl!ExFreePoolWithTag` at `0x140192732`
- `NETIO!NetioFreeNetBufferAndNetBufferList` at `0x14019270f`
- `NETIO!NetioFreeNetBufferAndNetBufferList` at `0x14019270f`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x1401926dd`
- `NETIO!NetioAllocateAndReferenceNetBufferAndNetBufferList` at `0x1401926dd`
- `fwpkclnt!FwppvSwitchCopyVmSwitchNblInfo` at `0x1401926fa`
- `fwpkclnt!FwppvSwitchCopyVmSwitchNblInfo` at `0x1401926fa`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14019278a`
- `fwpkclnt!FwppReferencevSwitchNblContext` at `0x14019278a`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x1401926b7`
- `fwpkclnt!FwppGetvSwitchNblContext` at `0x1401926b7`

## pseudocode

```c

```

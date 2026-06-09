# DirectComposition::CBatch::ReturnToApplication(bool)

- ea: `0x140089a0c`
- end: `0x140089ca1`
- name: `?ReturnToApplication@CBatch@DirectComposition@@QEAAX_N@Z`
- size: `661`
- prototype: `void __fastcall(PVOID Buffer, bool)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14007ad00`
- `0x1400fa8a4`
- `0x1401bad30`
- `0x14021d550`

## callees

- `0x14007b930`
- `0x1400887d0`
- `0x140089a0c`
- `0x14008a250`
- `0x140107648`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140089a72`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140089a72`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140089a49`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140089a49`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140089aa6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140089c09`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140089c67`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140089aa6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140089c09`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140089c67`
- `ntoskrnl!KeSetEvent` at `0x140089b66`
- `ntoskrnl!KeSetEvent` at `0x140089ba4`
- `ntoskrnl!KeSetEvent` at `0x140089be6`
- `ntoskrnl!KeSetEvent` at `0x140089b66`
- `ntoskrnl!KeSetEvent` at `0x140089ba4`
- `ntoskrnl!KeSetEvent` at `0x140089be6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140089a5a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140089a5a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140089b86`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140089b86`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089a9a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089bfd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089c5b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089a9a`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089bfd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089c5b`
- `ntoskrnl!ObfDereferenceObject` at `0x140089c2a`
- `ntoskrnl!ObfDereferenceObject` at `0x140089c2a`

## pseudocode

```c

```

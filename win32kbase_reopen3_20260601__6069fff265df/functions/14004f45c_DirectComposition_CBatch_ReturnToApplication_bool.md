# DirectComposition::CBatch::ReturnToApplication(bool)

- ea: `0x14004f45c`
- end: `0x14004f6f1`
- name: `?ReturnToApplication@CBatch@DirectComposition@@QEAAX_N@Z`
- size: `661`
- prototype: `void __fastcall(PVOID Buffer, bool)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140040590`
- `0x1400f7850`
- `0x1401ba110`
- `0x14021d4c0`

## callees

- `0x1400411c0`
- `0x14004e220`
- `0x14004f45c`
- `0x14004fca0`
- `0x1401048b8`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004f4c2`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14004f4c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004f499`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004f499`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f4f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f659`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f6b7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f4f6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f659`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004f6b7`
- `ntoskrnl!KeSetEvent` at `0x14004f5b6`
- `ntoskrnl!KeSetEvent` at `0x14004f5f4`
- `ntoskrnl!KeSetEvent` at `0x14004f636`
- `ntoskrnl!KeSetEvent` at `0x14004f5b6`
- `ntoskrnl!KeSetEvent` at `0x14004f5f4`
- `ntoskrnl!KeSetEvent` at `0x14004f636`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004f4aa`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004f4aa`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14004f5d6`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x14004f5d6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f4ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f64d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f6ab`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f4ea`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f64d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004f6ab`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f67a`
- `ntoskrnl!ObfDereferenceObject` at `0x14004f67a`

## pseudocode

```c

```

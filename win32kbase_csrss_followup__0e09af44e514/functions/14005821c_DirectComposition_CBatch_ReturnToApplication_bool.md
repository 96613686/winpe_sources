# DirectComposition::CBatch::ReturnToApplication(bool)

- ea: `0x14005821c`
- end: `0x1400584b1`
- name: `?ReturnToApplication@CBatch@DirectComposition@@QEAAX_N@Z`
- size: `661`
- prototype: `void __fastcall(PVOID Buffer, bool)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400494a0`
- `0x1400f5770`
- `0x1401b9bb0`
- `0x14021cca0`

## callees

- `0x14004a0d0`
- `0x140056fe0`
- `0x14005821c`
- `0x140058a60`
- `0x140100128`
- `0x140238240`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140058282`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140058282`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140058259`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140058259`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400582b6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140058419`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140058477`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400582b6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140058419`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140058477`
- `ntoskrnl!KeSetEvent` at `0x140058376`
- `ntoskrnl!KeSetEvent` at `0x1400583b4`
- `ntoskrnl!KeSetEvent` at `0x1400583f6`
- `ntoskrnl!KeSetEvent` at `0x140058376`
- `ntoskrnl!KeSetEvent` at `0x1400583b4`
- `ntoskrnl!KeSetEvent` at `0x1400583f6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005826a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005826a`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140058396`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140058396`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400582aa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005840d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005846b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400582aa`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005840d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005846b`
- `ntoskrnl!ObfDereferenceObject` at `0x14005843a`
- `ntoskrnl!ObfDereferenceObject` at `0x14005843a`

## pseudocode

```c

```

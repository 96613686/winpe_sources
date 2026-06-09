# RIMReadInput

- ea: `0x140070d30`
- end: `0x14007151c`
- name: `RIMReadInput`
- size: `2028`
- prototype: `__int64 __usercall@<rax>(HANDLE Handle@<rcx>, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140070960`
- `0x1401584d0`

## callees

- `0x140070d30`
- `0x140071524`
- `0x140071680`
- `0x1400718f8`
- `0x140071950`
- `0x1400723f8`
- `0x1400729c8`
- `0x140072a90`
- `0x1400775c0`
- `0x1401a9f9c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400713fc`
- `ntoskrnl!ZwClose` at `0x1400713fc`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140070e68`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140070f57`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140070e68`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140070f57`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140070e56`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140070f42`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140070e56`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140070f42`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400710c8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400710ea`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400710c8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400710ea`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400710bc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400710de`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400710bc`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400710de`
- `ntoskrnl!ExEventObjectType` at `0x140070e9d`
- `ntoskrnl!ExEventObjectType` at `0x140070ef6`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140070f15`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140070f15`
- `ntoskrnl!ExRawInputManagerObjectType` at `0x140070df3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140070e22`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140070ecb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140070e22`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140070ecb`
- `ntoskrnl!ObfDereferenceObject` at `0x140070f2e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400710f9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400711ea`
- `ntoskrnl!ObfDereferenceObject` at `0x140070f2e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400710f9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400711ea`
- `WIN32K!W32GetUserSessionState` at `0x140070d9a`
- `WIN32K!W32GetUserSessionState` at `0x140071043`
- `WIN32K!W32GetUserSessionState` at `0x140071160`
- `WIN32K!W32GetUserSessionState` at `0x1400712fe`
- `WIN32K!W32GetUserSessionState` at `0x140071341`
- `WIN32K!W32GetUserSessionState` at `0x14007142a`
- `WIN32K!W32GetUserSessionState` at `0x1400714cc`
- `WIN32K!W32GetUserSessionState` at `0x140070d9a`
- `WIN32K!W32GetUserSessionState` at `0x140071043`
- `WIN32K!W32GetUserSessionState` at `0x140071160`
- `WIN32K!W32GetUserSessionState` at `0x1400712fe`
- `WIN32K!W32GetUserSessionState` at `0x140071341`
- `WIN32K!W32GetUserSessionState` at `0x14007142a`
- `WIN32K!W32GetUserSessionState` at `0x1400714cc`

## pseudocode

```c

```

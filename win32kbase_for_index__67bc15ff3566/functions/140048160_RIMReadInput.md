# RIMReadInput

- ea: `0x140048160`
- end: `0x14004894c`
- name: `RIMReadInput`
- size: `2028`
- prototype: `__int64 __fastcall(char *Handle, __int64, __int64, void *, int, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140047d90`
- `0x14015b040`

## callees

- `0x140048160`
- `0x140048954`
- `0x140048ab0`
- `0x140048d28`
- `0x140048d80`
- `0x140049828`
- `0x140049df8`
- `0x140049ec0`
- `0x14004e9f0`
- `0x1401aab9c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14004882c`
- `ntoskrnl!ZwClose` at `0x14004882c`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140048298`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140048387`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140048298`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140048387`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140048286`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140048372`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140048286`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140048372`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400484f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004851a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400484f8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004851a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400484ec`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004850e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400484ec`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14004850e`
- `ntoskrnl!ExEventObjectType` at `0x1400482cd`
- `ntoskrnl!ExEventObjectType` at `0x140048326`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140048345`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140048345`
- `ntoskrnl!ExRawInputManagerObjectType` at `0x140048223`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140048252`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400482fb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140048252`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400482fb`
- `ntoskrnl!ObfDereferenceObject` at `0x14004835e`
- `ntoskrnl!ObfDereferenceObject` at `0x140048529`
- `ntoskrnl!ObfDereferenceObject` at `0x14004861a`
- `ntoskrnl!ObfDereferenceObject` at `0x14004835e`
- `ntoskrnl!ObfDereferenceObject` at `0x140048529`
- `ntoskrnl!ObfDereferenceObject` at `0x14004861a`
- `WIN32K!W32GetUserSessionState` at `0x1400481ca`
- `WIN32K!W32GetUserSessionState` at `0x140048473`
- `WIN32K!W32GetUserSessionState` at `0x140048590`
- `WIN32K!W32GetUserSessionState` at `0x14004872e`
- `WIN32K!W32GetUserSessionState` at `0x140048771`
- `WIN32K!W32GetUserSessionState` at `0x14004885a`
- `WIN32K!W32GetUserSessionState` at `0x1400488fc`
- `WIN32K!W32GetUserSessionState` at `0x1400481ca`
- `WIN32K!W32GetUserSessionState` at `0x140048473`
- `WIN32K!W32GetUserSessionState` at `0x140048590`
- `WIN32K!W32GetUserSessionState` at `0x14004872e`
- `WIN32K!W32GetUserSessionState` at `0x140048771`
- `WIN32K!W32GetUserSessionState` at `0x14004885a`
- `WIN32K!W32GetUserSessionState` at `0x1400488fc`

## pseudocode

```c

```

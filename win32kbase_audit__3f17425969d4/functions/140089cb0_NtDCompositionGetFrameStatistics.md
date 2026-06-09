# NtDCompositionGetFrameStatistics

- ea: `0x140089cb0`
- end: `0x140089ff6`
- name: `NtDCompositionGetFrameStatistics`
- size: `838`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140089cb0`
- `0x14008a250`
- `0x14008a284`
- `0x1400cef7c`
- `0x1401a81b0`
- `0x1402388e0`
- `0x1402bb054`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140089d0e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140089d50`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140089db3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140089d0e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140089d50`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140089db3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140089d8a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140089ded`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140089ec2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140089edd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140089d8a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140089ded`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140089ec2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140089edd`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140089e24`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140089e24`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140089d1e`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140089d1e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140089dc4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140089dc4`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140089d61`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140089d61`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089d7e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089de1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089eb6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089d7e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089de1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140089eb6`
- `WIN32K!W32GetDCompSessionState` at `0x140089d9b`
- `WIN32K!W32GetDCompSessionState` at `0x140089d9b`
- `HAL!KeQueryPerformanceCounter` at `0x140089e36`
- `HAL!KeQueryPerformanceCounter` at `0x140089f5c`
- `HAL!KeQueryPerformanceCounter` at `0x140089e36`
- `HAL!KeQueryPerformanceCounter` at `0x140089f5c`

## pseudocode

```c

```

# NtDCompositionGetFrameSurfaceUpdates

- ea: `0x1400d9810`
- end: `0x1400d9b04`
- name: `NtDCompositionGetFrameSurfaceUpdates`
- size: `756`
- prototype: `__int64 __fastcall(void *Src, void *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400d9810`
- `0x1400d9b0c`
- `0x1401c6028`
- `0x140238240`
- `0x1402bb054`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400d98b7`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400d98b7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d98cc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d990f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d9972`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d98cc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d990f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d9972`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d9949`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d99ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d9a93`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d9949`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d99ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400d9a93`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400d98dd`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400d98dd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400d9983`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400d9983`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400d9920`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400d9920`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400d993d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400d99a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400d993d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400d99a0`
- `WIN32K!W32GetDCompSessionState` at `0x1400d995a`
- `WIN32K!W32GetDCompSessionState` at `0x1400d995a`
- `WIN32K!W32GetUserSessionState` at `0x1400d98a4`
- `WIN32K!W32GetUserSessionState` at `0x1400d98a4`

## pseudocode

```c

```

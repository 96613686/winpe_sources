# NtDCompositionGetFrameSurfaceUpdates

- ea: `0x1400e3480`
- end: `0x1400e3774`
- name: `NtDCompositionGetFrameSurfaceUpdates`
- size: `756`
- prototype: `__int64 __fastcall(void *Src, void *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400e3480`
- `0x1400e377c`
- `0x1401c6588`
- `0x140238bf0`
- `0x1402bd054`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400e3527`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400e3527`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e353c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e357f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e35e2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e353c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e357f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400e35e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e35b9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e361c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e3703`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e35b9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e361c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400e3703`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400e354d`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400e354d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400e35f3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400e35f3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400e3590`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400e3590`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400e35ad`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400e3610`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400e35ad`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400e3610`
- `WIN32K!W32GetDCompSessionState` at `0x1400e35ca`
- `WIN32K!W32GetDCompSessionState` at `0x1400e35ca`
- `WIN32K!W32GetUserSessionState` at `0x1400e3514`
- `WIN32K!W32GetUserSessionState` at `0x1400e3514`

## pseudocode

```c

```

# NtDCompositionGetFrameSurfaceUpdates

- ea: `0x1400cec80`
- end: `0x1400cef74`
- name: `NtDCompositionGetFrameSurfaceUpdates`
- size: `756`
- prototype: `__int64 __fastcall(void *Src, void *, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400cec80`
- `0x1400cef7c`
- `0x1401c7158`
- `0x1402389c0`
- `0x1402bb054`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400ced27`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400ced27`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ced3c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ced7f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cede2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ced3c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400ced7f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400cede2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cedb9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cee1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cef03`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cedb9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cee1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400cef03`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400ced4d`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400ced4d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400cedf3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400cedf3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400ced90`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400ced90`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400cedad`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400cee10`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400cedad`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400cee10`
- `WIN32K!W32GetDCompSessionState` at `0x1400cedca`
- `WIN32K!W32GetDCompSessionState` at `0x1400cedca`
- `WIN32K!W32GetUserSessionState` at `0x1400ced14`
- `WIN32K!W32GetUserSessionState` at `0x1400ced14`

## pseudocode

```c

```

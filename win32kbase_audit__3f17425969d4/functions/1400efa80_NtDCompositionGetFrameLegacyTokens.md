# NtDCompositionGetFrameLegacyTokens

- ea: `0x1400efa80`
- end: `0x1400efdc5`
- name: `NtDCompositionGetFrameLegacyTokens`
- size: `837`
- prototype: `__int64 __fastcall(void *Src, void *, void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14007b930`
- `0x1400efa80`
- `0x1401ae7fc`
- `0x1401c7158`
- `0x1402389c0`
- `0x140238f80`
- `0x1402bb054`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1400efb21`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400efb21`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400efb36`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400efb74`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400efbd7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400efb36`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400efb74`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400efbd7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400efbae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400efc11`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400efd32`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400efbae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400efc11`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400efd32`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400efb48`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400efb48`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400efbe8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400efbe8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400efb85`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400efb85`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400efba2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400efc05`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400efba2`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400efc05`
- `WIN32K!W32GetDCompSessionState` at `0x1400efbbf`
- `WIN32K!W32GetDCompSessionState` at `0x1400efbbf`
- `WIN32K!W32GetUserSessionState` at `0x1400efb0e`
- `WIN32K!W32GetUserSessionState` at `0x1400efb0e`

## pseudocode

```c

```

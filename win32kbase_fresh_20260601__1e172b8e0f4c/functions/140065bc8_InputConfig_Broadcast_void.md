# InputConfig::Broadcast(void)

- ea: `0x140065bc8`
- end: `0x140065eac`
- name: `?Broadcast@InputConfig@@SAXXZ`
- size: `740`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140064538`
- `0x140065bb0`

## callees

- `0x1400411c0`
- `0x1400449b0`
- `0x140065bc8`
- `0x1400a3870`
- `0x1400a3924`
- `0x1401aa4fc`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140065bf3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140065bf3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140065c30`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140065c30`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140065c04`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140065c04`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140065c24`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140065c24`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140065c6d`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140065d89`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140065c6d`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140065d89`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140065ce9`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140065e66`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140065ce9`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140065e66`
- `WIN32K!W32GetUserSessionState` at `0x140065bdc`
- `WIN32K!W32GetUserSessionState` at `0x140065c44`
- `WIN32K!W32GetUserSessionState` at `0x140065c57`
- `WIN32K!W32GetUserSessionState` at `0x140065d73`
- `WIN32K!W32GetUserSessionState` at `0x140065bdc`
- `WIN32K!W32GetUserSessionState` at `0x140065c44`
- `WIN32K!W32GetUserSessionState` at `0x140065c57`
- `WIN32K!W32GetUserSessionState` at `0x140065d73`

## pseudocode

```c

```

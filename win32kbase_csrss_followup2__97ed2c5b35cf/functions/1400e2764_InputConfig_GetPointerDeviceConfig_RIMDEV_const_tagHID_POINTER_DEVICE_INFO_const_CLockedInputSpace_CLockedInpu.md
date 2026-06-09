# InputConfig::GetPointerDeviceConfig(RIMDEV const *,tagHID_POINTER_DEVICE_INFO const *,CLockedInputSpace *,CLockedInputSpaceRegion *)

- ea: `0x1400e2764`
- end: `0x1400e292e`
- name: `?GetPointerDeviceConfig@InputConfig@@SA_NPEBURIMDEV@@PEBUtagHID_POINTER_DEVICE_INFO@@PEAVCLockedInputSpace@@PEAVCLockedInputSpaceRegion@@@Z`
- size: `458`
- prototype: `static bool(const struct RIMDEV *, const struct tagHID_POINTER_DEVICE_INFO *, struct CLockedInputSpace *, struct CLockedInputSpaceRegion *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400e23e0`

## callees

- `0x1400e2764`
- `0x1400e2d2c`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400e27f2`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400e2872`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400e27f2`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400e2872`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400e281f`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400e28fc`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400e281f`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400e28fc`
- `WIN32K!W32GetUserSessionState` at `0x1400e2784`
- `WIN32K!W32GetUserSessionState` at `0x1400e27c4`
- `WIN32K!W32GetUserSessionState` at `0x1400e27dc`
- `WIN32K!W32GetUserSessionState` at `0x1400e285c`
- `WIN32K!W32GetUserSessionState` at `0x1400e2784`
- `WIN32K!W32GetUserSessionState` at `0x1400e27c4`
- `WIN32K!W32GetUserSessionState` at `0x1400e27dc`
- `WIN32K!W32GetUserSessionState` at `0x1400e285c`

## pseudocode

```c

```

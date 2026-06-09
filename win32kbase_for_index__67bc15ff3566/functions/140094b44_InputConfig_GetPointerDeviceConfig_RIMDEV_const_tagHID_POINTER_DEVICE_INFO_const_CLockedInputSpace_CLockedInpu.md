# InputConfig::GetPointerDeviceConfig(RIMDEV const *,tagHID_POINTER_DEVICE_INFO const *,CLockedInputSpace *,CLockedInputSpaceRegion *)

- ea: `0x140094b44`
- end: `0x140094d0e`
- name: `?GetPointerDeviceConfig@InputConfig@@SA_NPEBURIMDEV@@PEBUtagHID_POINTER_DEVICE_INFO@@PEAVCLockedInputSpace@@PEAVCLockedInputSpaceRegion@@@Z`
- size: `458`
- prototype: `static bool(const struct RIMDEV *, const struct tagHID_POINTER_DEVICE_INFO *, struct CLockedInputSpace *, struct CLockedInputSpaceRegion *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400947c0`

## callees

- `0x140094b44`
- `0x14011ade4`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140094bd2`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140094c52`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140094bd2`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140094c52`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140094bff`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140094cdc`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140094bff`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140094cdc`
- `WIN32K!W32GetUserSessionState` at `0x140094b64`
- `WIN32K!W32GetUserSessionState` at `0x140094ba4`
- `WIN32K!W32GetUserSessionState` at `0x140094bbc`
- `WIN32K!W32GetUserSessionState` at `0x140094c3c`
- `WIN32K!W32GetUserSessionState` at `0x140094b64`
- `WIN32K!W32GetUserSessionState` at `0x140094ba4`
- `WIN32K!W32GetUserSessionState` at `0x140094bbc`
- `WIN32K!W32GetUserSessionState` at `0x140094c3c`

## pseudocode

```c

```

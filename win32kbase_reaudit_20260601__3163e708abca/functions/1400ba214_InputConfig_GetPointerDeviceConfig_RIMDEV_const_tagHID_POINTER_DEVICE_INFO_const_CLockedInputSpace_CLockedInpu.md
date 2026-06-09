# InputConfig::GetPointerDeviceConfig(RIMDEV const *,tagHID_POINTER_DEVICE_INFO const *,CLockedInputSpace *,CLockedInputSpaceRegion *)

- ea: `0x1400ba214`
- end: `0x1400ba3de`
- name: `?GetPointerDeviceConfig@InputConfig@@SA_NPEBURIMDEV@@PEBUtagHID_POINTER_DEVICE_INFO@@PEAVCLockedInputSpace@@PEAVCLockedInputSpaceRegion@@@Z`
- size: `458`
- prototype: `static bool(const struct RIMDEV *, const struct tagHID_POINTER_DEVICE_INFO *, struct CLockedInputSpace *, struct CLockedInputSpaceRegion *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400b9e90`

## callees

- `0x1400ba214`
- `0x140117e04`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400ba2a2`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400ba322`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400ba2a2`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400ba322`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400ba2cf`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400ba3ac`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400ba2cf`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400ba3ac`
- `WIN32K!W32GetUserSessionState` at `0x1400ba234`
- `WIN32K!W32GetUserSessionState` at `0x1400ba274`
- `WIN32K!W32GetUserSessionState` at `0x1400ba28c`
- `WIN32K!W32GetUserSessionState` at `0x1400ba30c`
- `WIN32K!W32GetUserSessionState` at `0x1400ba234`
- `WIN32K!W32GetUserSessionState` at `0x1400ba274`
- `WIN32K!W32GetUserSessionState` at `0x1400ba28c`
- `WIN32K!W32GetUserSessionState` at `0x1400ba30c`

## pseudocode

```c

```

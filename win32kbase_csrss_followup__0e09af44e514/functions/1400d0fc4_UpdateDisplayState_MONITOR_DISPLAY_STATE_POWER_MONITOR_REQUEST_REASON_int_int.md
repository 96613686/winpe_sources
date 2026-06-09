# UpdateDisplayState(_MONITOR_DISPLAY_STATE,POWER_MONITOR_REQUEST_REASON,int,int)

- ea: `0x1400d0fc4`
- end: `0x1400d1382`
- name: `?UpdateDisplayState@@YAXW4_MONITOR_DISPLAY_STATE@@W4POWER_MONITOR_REQUEST_REASON@@HH@Z`
- size: `958`
- prototype: `void __fastcall(enum _MONITOR_DISPLAY_STATE, enum POWER_MONITOR_REQUEST_REASON, int, int)`
- caller_count: `3`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x1400a65c8`
- `0x1400a8620`
- `0x1401cdb70`

## callees

- `0x14001bdf0`
- `0x14001c470`
- `0x140031bf4`
- `0x140036118`
- `0x140077f50`
- `0x140078090`
- `0x140078120`
- `0x1400d0cb4`
- `0x1400d0fc4`
- `0x1400d1388`
- `0x1400d1620`
- `0x1400d1880`
- `0x1400d1c90`
- `0x1400d1ce8`
- `0x1400d2364`
- `0x1401ad430`
- `0x1401cd144`
- `0x140238160`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d11f3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400d11f3`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400d12de`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400d12de`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400d1113`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400d128e`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400d1113`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400d128e`
- `ntoskrnl!ZwPowerInformation` at `0x1400d11b0`
- `ntoskrnl!ZwPowerInformation` at `0x1400d11b0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d11e4`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400d11e4`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d1130`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400d1130`
- `WIN32K!W32GetUserSessionState` at `0x1400d100e`
- `WIN32K!W32GetUserSessionState` at `0x1400d107a`
- `WIN32K!W32GetUserSessionState` at `0x1400d10a3`
- `WIN32K!W32GetUserSessionState` at `0x1400d10bd`
- `WIN32K!W32GetUserSessionState` at `0x1400d11bc`
- `WIN32K!W32GetUserSessionState` at `0x1400d11d5`
- `WIN32K!W32GetUserSessionState` at `0x1400d100e`
- `WIN32K!W32GetUserSessionState` at `0x1400d107a`
- `WIN32K!W32GetUserSessionState` at `0x1400d10a3`
- `WIN32K!W32GetUserSessionState` at `0x1400d10bd`
- `WIN32K!W32GetUserSessionState` at `0x1400d11bc`
- `WIN32K!W32GetUserSessionState` at `0x1400d11d5`

## pseudocode

```c

```

# UpdateDisplayState(_MONITOR_DISPLAY_STATE,POWER_MONITOR_REQUEST_REASON,int,int)

- ea: `0x1400c3e10`
- end: `0x1400c41ce`
- name: `?UpdateDisplayState@@YAXW4_MONITOR_DISPLAY_STATE@@W4POWER_MONITOR_REQUEST_REASON@@HH@Z`
- size: `958`
- prototype: `void __fastcall(enum _MONITOR_DISPLAY_STATE, enum POWER_MONITOR_REQUEST_REASON, int, int)`
- caller_count: `3`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x1400cff38`
- `0x1400d1f90`
- `0x1401ce8f0`

## callees

- `0x140029710`
- `0x140029d90`
- `0x1400371c0`
- `0x14004f380`
- `0x14004f4c0`
- `0x14004f550`
- `0x1400c3ac4`
- `0x1400c3e10`
- `0x1400c41d4`
- `0x1400c4460`
- `0x1400c46c0`
- `0x1400c4ad0`
- `0x1400c4b28`
- `0x1400c51a4`
- `0x1400d7988`
- `0x1401ae470`
- `0x1401cdec4`
- `0x1402388e0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c403f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c403f`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400c412a`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x1400c412a`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400c3f5f`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400c40da`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400c3f5f`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x1400c40da`
- `ntoskrnl!ZwPowerInformation` at `0x1400c3ffc`
- `ntoskrnl!ZwPowerInformation` at `0x1400c3ffc`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c4030`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400c4030`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400c3f7c`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400c3f7c`
- `WIN32K!W32GetUserSessionState` at `0x1400c3e5a`
- `WIN32K!W32GetUserSessionState` at `0x1400c3ec6`
- `WIN32K!W32GetUserSessionState` at `0x1400c3eef`
- `WIN32K!W32GetUserSessionState` at `0x1400c3f09`
- `WIN32K!W32GetUserSessionState` at `0x1400c4008`
- `WIN32K!W32GetUserSessionState` at `0x1400c4021`
- `WIN32K!W32GetUserSessionState` at `0x1400c3e5a`
- `WIN32K!W32GetUserSessionState` at `0x1400c3ec6`
- `WIN32K!W32GetUserSessionState` at `0x1400c3eef`
- `WIN32K!W32GetUserSessionState` at `0x1400c3f09`
- `WIN32K!W32GetUserSessionState` at `0x1400c4008`
- `WIN32K!W32GetUserSessionState` at `0x1400c4021`

## pseudocode

```c

```

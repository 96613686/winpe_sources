# UpdateDisplayState(_MONITOR_DISPLAY_STATE,POWER_MONITOR_REQUEST_REASON,int,int)

- ea: `0x140060b24`
- end: `0x140060ee2`
- name: `?UpdateDisplayState@@YAXW4_MONITOR_DISPLAY_STATE@@W4POWER_MONITOR_REQUEST_REASON@@HH@Z`
- size: `958`
- prototype: `void __fastcall(enum _MONITOR_DISPLAY_STATE, enum POWER_MONITOR_REQUEST_REASON, int, int)`
- caller_count: `3`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x1400c0e98`
- `0x1400c2ef0`
- `0x1401ce0d0`

## callees

- `0x140012c80`
- `0x140013300`
- `0x140028974`
- `0x14002ce98`
- `0x140060814`
- `0x140060b24`
- `0x140060ee8`
- `0x140061180`
- `0x1400613e0`
- `0x1400617f0`
- `0x140061848`
- `0x140061ec4`
- `0x140076db0`
- `0x140076ef0`
- `0x140076f80`
- `0x1401ad990`
- `0x1401cd6a4`
- `0x140238b10`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140060d53`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140060d53`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140060e3e`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceShared` at `0x140060e3e`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140060c73`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140060dee`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140060c73`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140060dee`
- `ntoskrnl!ZwPowerInformation` at `0x140060d10`
- `ntoskrnl!ZwPowerInformation` at `0x140060d10`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140060d44`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140060d44`
- `WIN32K!W32GetUserGdiSessionState` at `0x140060c90`
- `WIN32K!W32GetUserGdiSessionState` at `0x140060c90`
- `WIN32K!W32GetUserSessionState` at `0x140060b6e`
- `WIN32K!W32GetUserSessionState` at `0x140060bda`
- `WIN32K!W32GetUserSessionState` at `0x140060c03`
- `WIN32K!W32GetUserSessionState` at `0x140060c1d`
- `WIN32K!W32GetUserSessionState` at `0x140060d1c`
- `WIN32K!W32GetUserSessionState` at `0x140060d35`
- `WIN32K!W32GetUserSessionState` at `0x140060b6e`
- `WIN32K!W32GetUserSessionState` at `0x140060bda`
- `WIN32K!W32GetUserSessionState` at `0x140060c03`
- `WIN32K!W32GetUserSessionState` at `0x140060c1d`
- `WIN32K!W32GetUserSessionState` at `0x140060d1c`
- `WIN32K!W32GetUserSessionState` at `0x140060d35`

## pseudocode

```c

```

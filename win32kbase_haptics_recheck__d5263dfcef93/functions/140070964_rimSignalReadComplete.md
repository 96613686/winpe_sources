# rimSignalReadComplete

- ea: `0x140070964`
- end: `0x140070e53`
- name: `rimSignalReadComplete`
- size: `1263`
- prototype: `__int64 __fastcall(struct RawInputManagerObject *, struct RIMDEV *, struct _IO_STATUS_BLOCK *)`
- caller_count: `3`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400e8c70`
- `0x14011fd08`
- `0x140134940`

## callees

- `0x140070964`
- `0x140070e5c`
- `0x140070f48`
- `0x140070fa0`
- `0x140071258`
- `0x14009e72c`
- `0x1400cb450`
- `0x1400ea514`
- `0x1402089ec`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140070b61`
- `ntoskrnl!ZwClose` at `0x140070b61`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400709ce`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400709ce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400709bd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400709bd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070a43`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140070a43`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140070a37`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140070a37`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140070bc0`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140070bc0`
- `ntoskrnl!ZwSetEvent` at `0x140070b4e`
- `ntoskrnl!ZwSetEvent` at `0x140070b4e`
- `ntoskrnl!KeSetTimer` at `0x140070e30`
- `ntoskrnl!KeSetTimer` at `0x140070e30`
- `WIN32K!W32GetUserSessionState` at `0x1400709ad`
- `WIN32K!W32GetUserSessionState` at `0x140070a08`
- `WIN32K!W32GetUserSessionState` at `0x140070a21`
- `WIN32K!W32GetUserSessionState` at `0x140070aa9`
- `WIN32K!W32GetUserSessionState` at `0x140070c0d`
- `WIN32K!W32GetUserSessionState` at `0x140070cb4`
- `WIN32K!W32GetUserSessionState` at `0x140070d84`
- `WIN32K!W32GetUserSessionState` at `0x140070de7`
- `WIN32K!W32GetUserSessionState` at `0x140070e00`
- `WIN32K!W32GetUserSessionState` at `0x140070e13`
- `WIN32K!W32GetUserSessionState` at `0x1400709ad`
- `WIN32K!W32GetUserSessionState` at `0x140070a08`
- `WIN32K!W32GetUserSessionState` at `0x140070a21`
- `WIN32K!W32GetUserSessionState` at `0x140070aa9`
- `WIN32K!W32GetUserSessionState` at `0x140070c0d`
- `WIN32K!W32GetUserSessionState` at `0x140070cb4`
- `WIN32K!W32GetUserSessionState` at `0x140070d84`
- `WIN32K!W32GetUserSessionState` at `0x140070de7`
- `WIN32K!W32GetUserSessionState` at `0x140070e00`
- `WIN32K!W32GetUserSessionState` at `0x140070e13`
- `HAL!KeQueryPerformanceCounter` at `0x1400709e9`
- `HAL!KeQueryPerformanceCounter` at `0x140070b07`
- `HAL!KeQueryPerformanceCounter` at `0x1400709e9`
- `HAL!KeQueryPerformanceCounter` at `0x140070b07`

## pseudocode

```c

```

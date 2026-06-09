# xxxWaitForVideoPortCalloutReady(uchar,uchar,_DXGK_DISPLAY_SCENARIO_CONTEXT *)

- ea: `0x140160a84`
- end: `0x140160cb1`
- name: `?xxxWaitForVideoPortCalloutReady@@YAXEEPEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@@Z`
- size: `557`
- prototype: `void __fastcall(__int64, __int64, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x1401141a8`

## callees

- `0x140029710`
- `0x140029d90`
- `0x140035ecc`
- `0x14004f380`
- `0x14004f4c0`
- `0x14004f550`
- `0x1400d7988`
- `0x140160a84`
- `0x140160cb8`
- `0x140160d2c`
- `0x140160d84`
- `0x14017ada0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140160b62`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140160b62`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140160b35`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140160b35`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140160b53`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140160b53`
- `WIN32K!W32GetUserGdiSessionState` at `0x140160ab6`
- `WIN32K!W32GetUserGdiSessionState` at `0x140160bee`
- `WIN32K!W32GetUserGdiSessionState` at `0x140160c27`
- `WIN32K!W32GetUserGdiSessionState` at `0x140160ab6`
- `WIN32K!W32GetUserGdiSessionState` at `0x140160bee`
- `WIN32K!W32GetUserGdiSessionState` at `0x140160c27`
- `WIN32K!W32GetUserSessionState` at `0x140160b44`
- `WIN32K!W32GetUserSessionState` at `0x140160c53`
- `WIN32K!W32GetUserSessionState` at `0x140160c6d`
- `WIN32K!W32GetUserSessionState` at `0x140160b44`
- `WIN32K!W32GetUserSessionState` at `0x140160c53`
- `WIN32K!W32GetUserSessionState` at `0x140160c6d`

## pseudocode

```c

```

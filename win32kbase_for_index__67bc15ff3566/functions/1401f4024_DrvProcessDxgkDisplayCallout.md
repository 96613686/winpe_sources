# DrvProcessDxgkDisplayCallout

- ea: `0x1401f4024`
- end: `0x1401f43a1`
- name: `DrvProcessDxgkDisplayCallout`
- size: `893`
- prototype: `__int64 __usercall@<rax>(struct tagDESKTOP *@<rcx>, unsigned __int8 *@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1401141a8`

## callees

- `0x1401147dc`
- `0x14014065c`
- `0x14018b50c`
- `0x1401efdf0`
- `0x1401f0730`
- `0x1401f4024`
- `0x1401f43b0`
- `0x1402388e0`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1401f413c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1401f413c`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401f416f`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401f416f`
- `watchdog!WdLogSingleEntry0` at `0x1401f429c`
- `watchdog!WdLogSingleEntry0` at `0x1401f429c`
- `watchdog!WdLogSingleEntry1` at `0x1401f40ba`
- `watchdog!WdLogSingleEntry1` at `0x1401f40ba`
- `watchdog!WdLogSingleEntry2` at `0x1401f418b`
- `watchdog!WdLogSingleEntry2` at `0x1401f4242`
- `watchdog!WdLogSingleEntry2` at `0x1401f42f7`
- `watchdog!WdLogSingleEntry2` at `0x1401f418b`
- `watchdog!WdLogSingleEntry2` at `0x1401f4242`
- `watchdog!WdLogSingleEntry2` at `0x1401f42f7`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f408e`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f408e`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401f4280`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401f4280`
- `WIN32K!W32GetUserSessionState` at `0x1401f41d7`
- `WIN32K!W32GetUserSessionState` at `0x1401f4319`
- `WIN32K!W32GetUserSessionState` at `0x1401f434b`
- `WIN32K!W32GetUserSessionState` at `0x1401f41d7`
- `WIN32K!W32GetUserSessionState` at `0x1401f4319`
- `WIN32K!W32GetUserSessionState` at `0x1401f434b`

## pseudocode

```c

```

# DrvProcessDxgkDisplayCallout

- ea: `0x1401f3f84`
- end: `0x1401f4301`
- name: `DrvProcessDxgkDisplayCallout`
- size: `893`
- prototype: `__int64 __usercall@<rax>(struct tagDESKTOP *@<rcx>, unsigned __int8 *@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x140111808`

## callees

- `0x140111e3c`
- `0x14013de9c`
- `0x140188a6c`
- `0x1401efd50`
- `0x1401f0690`
- `0x1401f3f84`
- `0x1401f4310`
- `0x140238b10`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1401f409c`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1401f409c`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401f40cf`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401f40cf`
- `watchdog!WdLogSingleEntry0` at `0x1401f41fc`
- `watchdog!WdLogSingleEntry0` at `0x1401f41fc`
- `watchdog!WdLogSingleEntry1` at `0x1401f401a`
- `watchdog!WdLogSingleEntry1` at `0x1401f401a`
- `watchdog!WdLogSingleEntry2` at `0x1401f40eb`
- `watchdog!WdLogSingleEntry2` at `0x1401f41a2`
- `watchdog!WdLogSingleEntry2` at `0x1401f4257`
- `watchdog!WdLogSingleEntry2` at `0x1401f40eb`
- `watchdog!WdLogSingleEntry2` at `0x1401f41a2`
- `watchdog!WdLogSingleEntry2` at `0x1401f4257`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f3fee`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f3fee`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401f41e0`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401f41e0`
- `WIN32K!W32GetUserSessionState` at `0x1401f4137`
- `WIN32K!W32GetUserSessionState` at `0x1401f4279`
- `WIN32K!W32GetUserSessionState` at `0x1401f42ab`
- `WIN32K!W32GetUserSessionState` at `0x1401f4137`
- `WIN32K!W32GetUserSessionState` at `0x1401f4279`
- `WIN32K!W32GetUserSessionState` at `0x1401f42ab`

## pseudocode

```c

```

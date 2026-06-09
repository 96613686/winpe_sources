# DrvProcessDxgkDisplayCallout

- ea: `0x1401f37c4`
- end: `0x1401f3b41`
- name: `DrvProcessDxgkDisplayCallout`
- size: `893`
- prototype: `__int64 __usercall@<rax>(struct tagDESKTOP *@<rcx>, unsigned __int8 *@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x140111338`

## callees

- `0x14011196c`
- `0x14013e47c`
- `0x140189bcc`
- `0x1401ef590`
- `0x1401efed0`
- `0x1401f37c4`
- `0x1401f3b50`
- `0x140238160`
- `0x140238240`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1401f38dc`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x1401f38dc`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401f390f`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401f390f`
- `watchdog!WdLogSingleEntry0` at `0x1401f3a3c`
- `watchdog!WdLogSingleEntry0` at `0x1401f3a3c`
- `watchdog!WdLogSingleEntry1` at `0x1401f385a`
- `watchdog!WdLogSingleEntry1` at `0x1401f385a`
- `watchdog!WdLogSingleEntry2` at `0x1401f392b`
- `watchdog!WdLogSingleEntry2` at `0x1401f39e2`
- `watchdog!WdLogSingleEntry2` at `0x1401f3a97`
- `watchdog!WdLogSingleEntry2` at `0x1401f392b`
- `watchdog!WdLogSingleEntry2` at `0x1401f39e2`
- `watchdog!WdLogSingleEntry2` at `0x1401f3a97`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f382e`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401f382e`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401f3a20`
- `WIN32K!W32GetUserGdiSessionState` at `0x1401f3a20`
- `WIN32K!W32GetUserSessionState` at `0x1401f3977`
- `WIN32K!W32GetUserSessionState` at `0x1401f3ab9`
- `WIN32K!W32GetUserSessionState` at `0x1401f3aeb`
- `WIN32K!W32GetUserSessionState` at `0x1401f3977`
- `WIN32K!W32GetUserSessionState` at `0x1401f3ab9`
- `WIN32K!W32GetUserSessionState` at `0x1401f3aeb`

## pseudocode

```c

```

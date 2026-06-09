# Win32kNtUserCleanup(void)

- ea: `0x1401acc10`
- end: `0x1401ace76`
- name: `?Win32kNtUserCleanup@@YAHXZ`
- size: `614`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x1401cebd0`

## callees

- `0x140012c80`
- `0x140013300`
- `0x14002ce98`
- `0x1400718f0`
- `0x140076db0`
- `0x140076ef0`
- `0x140076f80`
- `0x14014cf44`
- `0x1401812a8`
- `0x140185d94`
- `0x140195f7c`
- `0x1401a5ce0`
- `0x1401acc10`
- `0x1401ace80`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1401ace0f`
- `ntoskrnl!ZwClose` at `0x1401ace0f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401acd26`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401acd26`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1401acd17`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1401acd17`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401acce7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401acdb8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401acdd9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ace25`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ace47`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401acce7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401acdb8`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401acdd9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ace25`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ace47`
- `WIN32K!W32GetUserSessionState` at `0x1401acc5d`
- `WIN32K!W32GetUserSessionState` at `0x1401accaa`
- `WIN32K!W32GetUserSessionState` at `0x1401accc4`
- `WIN32K!W32GetUserSessionState` at `0x1401acd08`
- `WIN32K!W32GetUserSessionState` at `0x1401acd9d`
- `WIN32K!W32GetUserSessionState` at `0x1401acdf7`
- `WIN32K!W32GetUserSessionState` at `0x1401acc5d`
- `WIN32K!W32GetUserSessionState` at `0x1401accaa`
- `WIN32K!W32GetUserSessionState` at `0x1401accc4`
- `WIN32K!W32GetUserSessionState` at `0x1401acd08`
- `WIN32K!W32GetUserSessionState` at `0x1401acd9d`
- `WIN32K!W32GetUserSessionState` at `0x1401acdf7`

## pseudocode

```c

```

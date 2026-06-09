# _AllowSetForegroundWindow(ulong,AllowSetForegroundWindowPolicy)

- ea: `0x14017af68`
- end: `0x14017b665`
- name: `?_AllowSetForegroundWindow@@YA?AW4AllowSetForegroundWindowResult@@KW4AllowSetForegroundWindowPolicy@@@Z`
- size: `1789`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14017aaa0`

## callees

- `0x1400c636c`
- `0x1400dd43c`
- `0x1400e2cb0`
- `0x140179cc4`
- `0x14017af68`
- `0x14017bc34`
- `0x14017c9bc`
- `0x14017cbc4`
- `0x14017cc14`
- `0x14021a788`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14017b018`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14017b018`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14017b331`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14017b331`
- `win32kbase!?Set@LastWokenThread@@YAXPEBUtagTHREADINFO@@W4LastWokenThreadPurpose@@_N@Z` at `0x14017b179`
- `win32kbase!?Set@LastWokenThread@@YAXPEBUtagTHREADINFO@@W4LastWokenThreadPurpose@@_N@Z` at `0x14017b179`
- `win32kbase!?Clear@LastWokenThread@@YAXXZ` at `0x14017b26a`
- `win32kbase!?Clear@LastWokenThread@@YAXXZ` at `0x14017b379`
- `win32kbase!?Clear@LastWokenThread@@YAXXZ` at `0x14017b26a`
- `win32kbase!?Clear@LastWokenThread@@YAXXZ` at `0x14017b379`
- `win32kbase!?Test@LastWokenThread@@YA?AW4LastWokenThreadTestResult@@PEBUtagPROCESSINFO@@_N@Z` at `0x14017b62f`
- `win32kbase!?Test@LastWokenThread@@YA?AW4LastWokenThreadTestResult@@PEBUtagPROCESSINFO@@_N@Z` at `0x14017b62f`
- `win32kbase!IsDesktopApp` at `0x14017b159`
- `win32kbase!IsDesktopApp` at `0x14017b159`
- `WIN32K!W32GetUserSessionState` at `0x14017afd1`
- `WIN32K!W32GetUserSessionState` at `0x14017b0b0`
- `WIN32K!W32GetUserSessionState` at `0x14017b21f`
- `WIN32K!W32GetUserSessionState` at `0x14017b2b6`
- `WIN32K!W32GetUserSessionState` at `0x14017b3ca`
- `WIN32K!W32GetUserSessionState` at `0x14017b419`
- `WIN32K!W32GetUserSessionState` at `0x14017b45a`
- `WIN32K!W32GetUserSessionState` at `0x14017b4c6`
- `WIN32K!W32GetUserSessionState` at `0x14017b51f`
- `WIN32K!W32GetUserSessionState` at `0x14017afd1`
- `WIN32K!W32GetUserSessionState` at `0x14017b0b0`
- `WIN32K!W32GetUserSessionState` at `0x14017b21f`
- `WIN32K!W32GetUserSessionState` at `0x14017b2b6`
- `WIN32K!W32GetUserSessionState` at `0x14017b3ca`
- `WIN32K!W32GetUserSessionState` at `0x14017b419`
- `WIN32K!W32GetUserSessionState` at `0x14017b45a`
- `WIN32K!W32GetUserSessionState` at `0x14017b4c6`
- `WIN32K!W32GetUserSessionState` at `0x14017b51f`

## pseudocode

```c

```

# Win32kNtUserCleanup(void)

- ea: `0x1401ac6b0`
- end: `0x1401ac916`
- name: `?Win32kNtUserCleanup@@YAHXZ`
- size: `614`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x1401ce670`

## callees

- `0x14001bdf0`
- `0x14001c470`
- `0x140036118`
- `0x140072a90`
- `0x140077f50`
- `0x140078090`
- `0x140078120`
- `0x14014d9f4`
- `0x140181bf8`
- `0x140186ef4`
- `0x1401960ac`
- `0x1401a5780`
- `0x1401ac6b0`
- `0x1401ac920`
- `0x140238240`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1401ac8af`
- `ntoskrnl!ZwClose` at `0x1401ac8af`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ac7c6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ac7c6`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1401ac7b7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1401ac7b7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ac787`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ac858`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ac879`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ac8c5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ac8e7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ac787`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ac858`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ac879`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ac8c5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ac8e7`
- `WIN32K!W32GetUserSessionState` at `0x1401ac6fd`
- `WIN32K!W32GetUserSessionState` at `0x1401ac74a`
- `WIN32K!W32GetUserSessionState` at `0x1401ac764`
- `WIN32K!W32GetUserSessionState` at `0x1401ac7a8`
- `WIN32K!W32GetUserSessionState` at `0x1401ac83d`
- `WIN32K!W32GetUserSessionState` at `0x1401ac897`
- `WIN32K!W32GetUserSessionState` at `0x1401ac6fd`
- `WIN32K!W32GetUserSessionState` at `0x1401ac74a`
- `WIN32K!W32GetUserSessionState` at `0x1401ac764`
- `WIN32K!W32GetUserSessionState` at `0x1401ac7a8`
- `WIN32K!W32GetUserSessionState` at `0x1401ac83d`
- `WIN32K!W32GetUserSessionState` at `0x1401ac897`

## pseudocode

```c

```

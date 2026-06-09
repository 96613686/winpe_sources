# Win32kNtUserCleanup(void)

- ea: `0x1401ad2b0`
- end: `0x1401ad516`
- name: `?Win32kNtUserCleanup@@YAHXZ`
- size: `614`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x1401cf3f0`

## callees

- `0x140029710`
- `0x140029d90`
- `0x140049ec0`
- `0x14004f380`
- `0x14004f4c0`
- `0x14004f550`
- `0x1400d7988`
- `0x14014f9c4`
- `0x140183768`
- `0x140185a64`
- `0x140188cc4`
- `0x1401a6310`
- `0x1401ad2b0`
- `0x1401ad520`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1401ad4af`
- `ntoskrnl!ZwClose` at `0x1401ad4af`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ad3c6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1401ad3c6`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1401ad3b7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1401ad3b7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ad387`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ad458`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ad479`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ad4c5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ad4e7`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ad387`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ad458`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ad479`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ad4c5`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ad4e7`
- `WIN32K!W32GetUserSessionState` at `0x1401ad2fd`
- `WIN32K!W32GetUserSessionState` at `0x1401ad34a`
- `WIN32K!W32GetUserSessionState` at `0x1401ad364`
- `WIN32K!W32GetUserSessionState` at `0x1401ad3a8`
- `WIN32K!W32GetUserSessionState` at `0x1401ad43d`
- `WIN32K!W32GetUserSessionState` at `0x1401ad497`
- `WIN32K!W32GetUserSessionState` at `0x1401ad2fd`
- `WIN32K!W32GetUserSessionState` at `0x1401ad34a`
- `WIN32K!W32GetUserSessionState` at `0x1401ad364`
- `WIN32K!W32GetUserSessionState` at `0x1401ad3a8`
- `WIN32K!W32GetUserSessionState` at `0x1401ad43d`
- `WIN32K!W32GetUserSessionState` at `0x1401ad497`

## pseudocode

```c

```

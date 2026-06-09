# DEVLOCKOBJ::bDisposeTrgDcoWorker(void)

- ea: `0x14005d6e0`
- end: `0x14005da85`
- name: `?bDisposeTrgDcoWorker@DEVLOCKOBJ@@QEAAHXZ`
- size: `933`
- prototype: `__int64 __fastcall(DEVLOCKOBJ *this, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x14005d010`
- `0x14005e480`

## callees

- `0x14005d6e0`
- `0x14005da8c`
- `0x14005db98`
- `0x14005e5d4`
- `0x140099c84`
- `0x140291ec8`
- `0x1402920cc`
- `0x140343080`

## import_xrefs

- `ntoskrnl!KeIsAttachedProcess` at `0x14005d91c`
- `ntoskrnl!KeIsAttachedProcess` at `0x14005d91c`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14005da14`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x14005da14`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005d7d5`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005d7d5`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14005da06`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14005da23`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14005da06`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14005da23`
- `ntoskrnl!PsGetCurrentProcess` at `0x14005d9f7`
- `ntoskrnl!PsGetCurrentProcess` at `0x14005d9f7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14005d8d7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14005d8d7`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14005d933`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x14005d933`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005d88f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005d88f`
- `win32kbase!HmgPentryFromPobj` at `0x14005d7fa`
- `win32kbase!HmgPentryFromPobj` at `0x14005d7fa`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14005d966`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14005da3c`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14005da3c`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14005d907`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14005d907`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x14005d8a8`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x14005d8a8`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14005d82d`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14005d82d`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005d816`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005d816`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005da6d`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005da6d`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x14005d769`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x14005d769`

## pseudocode

```c

```

# DEVLOCKOBJ::bDisposeTrgDcoWorker(void)

- ea: `0x140084210`
- end: `0x1400845b5`
- name: `?bDisposeTrgDcoWorker@DEVLOCKOBJ@@QEAAHXZ`
- size: `933`
- prototype: `__int64 __fastcall(DEVLOCKOBJ *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x140080590`
- `0x140083c50`

## callees

- `0x14005f380`
- `0x1400835e4`
- `0x140084210`
- `0x1400845bc`
- `0x1400846c8`
- `0x14028f9d8`
- `0x14028fbdc`
- `0x1403420d0`

## import_xrefs

- `ntoskrnl!KeIsAttachedProcess` at `0x14008444c`
- `ntoskrnl!KeIsAttachedProcess` at `0x14008444c`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140084544`
- `ntoskrnl!PsGetCurrentThreadProcess` at `0x140084544`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140084305`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140084305`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140084536`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140084553`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140084536`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140084553`
- `ntoskrnl!PsGetCurrentProcess` at `0x140084527`
- `ntoskrnl!PsGetCurrentProcess` at `0x140084527`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140084407`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140084407`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140084463`
- `ntoskrnl!PsGetThreadWin32Thread` at `0x140084463`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400843bf`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400843bf`
- `win32kbase!HmgPentryFromPobj` at `0x14008432a`
- `win32kbase!HmgPentryFromPobj` at `0x14008432a`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140084496`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14008456c`
- `win32kbase!?GrepOnAllLocksReleased@@YAXXZ` at `0x14008456c`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140084437`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140084437`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x1400843d8`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x1400843d8`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14008435d`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14008435d`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140084346`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140084346`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14008459d`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14008459d`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140084299`
- `win32kbase!?bUnMap@SURFACE@@QEAAHXZ` at `0x140084299`

## pseudocode

```c

```

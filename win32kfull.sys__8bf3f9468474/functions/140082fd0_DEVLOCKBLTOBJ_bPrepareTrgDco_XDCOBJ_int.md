# DEVLOCKBLTOBJ::bPrepareTrgDco(XDCOBJ *,int)

- ea: `0x140082fd0`
- end: `0x14008352c`
- name: `?bPrepareTrgDco@DEVLOCKBLTOBJ@@QEAAHPEAVXDCOBJ@@H@Z`
- size: `1372`
- prototype: `__int64 __fastcall(DEVLOCKBLTOBJ *__hidden this, struct XDCOBJ *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140068f04`
- `0x14006d614`
- `0x140302ddc`

## callees

- `0x14005f380`
- `0x1400604f0`
- `0x140082fd0`
- `0x140083534`
- `0x1400845bc`
- `0x1400846c8`
- `0x140175230`
- `0x14017fad8`
- `0x1401b6a2c`
- `0x14029d748`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14008305d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400831a1`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14008305d`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400831a1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400832c7`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400832c7`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140083318`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140083318`
- `win32kbase!HmgPentryFromPobj` at `0x140083084`
- `win32kbase!HmgPentryFromPobj` at `0x1400831c6`
- `win32kbase!HmgPentryFromPobj` at `0x140083084`
- `win32kbase!HmgPentryFromPobj` at `0x1400831c6`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140083368`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x140083368`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140083354`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x140083354`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140083331`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x140083331`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x1400831fa`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x1400831fa`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x1400830a6`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x1400831e3`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x1400830a6`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x1400831e3`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140083489`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x1400834fa`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140083489`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x1400834fa`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x1400830c0`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x1400830c0`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x140083442`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x140083442`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14008342c`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14008342c`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140083021`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x140083021`
- `win32kbase!?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ` at `0x14008314d`
- `win32kbase!?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ` at `0x14008314d`

## pseudocode

```c

```

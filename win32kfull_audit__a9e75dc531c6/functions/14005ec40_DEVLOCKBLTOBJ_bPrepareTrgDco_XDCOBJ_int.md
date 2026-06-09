# DEVLOCKBLTOBJ::bPrepareTrgDco(XDCOBJ *,int)

- ea: `0x14005ec40`
- end: `0x14005f19c`
- name: `?bPrepareTrgDco@DEVLOCKBLTOBJ@@QEAAHPEAVXDCOBJ@@H@Z`
- size: `1372`
- prototype: `__int64 __fastcall(DEVLOCKBLTOBJ *this, struct XDCOBJ *, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140065000`
- `0x14009bf24`

## callees

- `0x1400539b0`
- `0x14005da8c`
- `0x14005db98`
- `0x14005ec40`
- `0x14005f1a4`
- `0x140099c84`
- `0x140169010`
- `0x14018cdb8`
- `0x1401b331c`
- `0x14029fc18`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14005eccd`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005ee11`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005eccd`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005ee11`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14005ef37`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14005ef37`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005ef88`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005ef88`
- `win32kbase!HmgPentryFromPobj` at `0x14005ecf4`
- `win32kbase!HmgPentryFromPobj` at `0x14005ee36`
- `win32kbase!HmgPentryFromPobj` at `0x14005ecf4`
- `win32kbase!HmgPentryFromPobj` at `0x14005ee36`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14005efd8`
- `win32kbase!GreReleaseSemaphoreSharedInternal` at `0x14005efd8`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14005efc4`
- `win32kbase!EtwTraceGreLockReleaseSemaphore` at `0x14005efc4`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x14005efa1`
- `win32kbase!GreAcquireSemaphoreSharedInternal` at `0x14005efa1`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14005ee6a`
- `win32kbase!?RestoreAttributes@DC@@QEAAXPEAU_DC_ATTR@@@Z` at `0x14005ee6a`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005ed16`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005ee53`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005ed16`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005ee53`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005f0f9`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005f16a`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005f0f9`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005f16a`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14005ed30`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14005ed30`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14005f0b2`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14005f0b2`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14005f09c`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14005f09c`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14005ec91`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14005ec91`
- `win32kbase!?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ` at `0x14005edbd`
- `win32kbase!?Map@SURFACE@@QEAA?AW4SurfaceMapStatus@1@XZ` at `0x14005edbd`

## pseudocode

```c

```

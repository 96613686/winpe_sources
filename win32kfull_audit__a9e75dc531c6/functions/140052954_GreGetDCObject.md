# GreGetDCObject

- ea: `0x140052954`
- end: `0x140052d47`
- name: `GreGetDCObject`
- size: `1011`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1401ef8b0`

## callees

- `0x140052954`
- `0x1400539b0`
- `0x14005b820`
- `0x14005d010`
- `0x14006bd2c`
- `0x1400a4e80`
- `0x140154d18`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x140052a2a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x140052a2a`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140052996`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140052bee`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140052996`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140052bee`
- `win32kbase!HmgPentryFromPobj` at `0x140052a52`
- `win32kbase!HmgPentryFromPobj` at `0x140052a52`
- `win32kbase!PushThreadGuardedObject` at `0x1400529d3`
- `win32kbase!PushThreadGuardedObject` at `0x140052add`
- `win32kbase!PushThreadGuardedObject` at `0x1400529d3`
- `win32kbase!PushThreadGuardedObject` at `0x140052add`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140052a71`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x140052a71`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140052d00`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x140052d00`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x140052a8a`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x140052a8a`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x140052c7c`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x140052c7c`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140052970`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140052c68`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140052970`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x140052c68`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400529ed`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x1400529ed`
- `win32kbase!?vLockNoDrawing@DEVLOCKOBJ@@QEAAXAEAVXDCOBJ@@@Z` at `0x140052be2`
- `win32kbase!?vLockNoDrawing@DEVLOCKOBJ@@QEAAXAEAVXDCOBJ@@@Z` at `0x140052be2`
- `win32kbase!GreDCSelectBrush` at `0x140052b47`
- `win32kbase!GreDCSelectBrush` at `0x140052b47`
- `win32kbase!GreDCSelectPen` at `0x140052b6f`
- `win32kbase!GreDCSelectPen` at `0x140052b6f`
- `win32kbase!GreGetStockObject` at `0x140052cac`
- `win32kbase!GreGetStockObject` at `0x140052cac`

## pseudocode

```c

```

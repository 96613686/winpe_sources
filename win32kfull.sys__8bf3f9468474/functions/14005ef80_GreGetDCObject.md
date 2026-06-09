# GreGetDCObject

- ea: `0x14005ef80`
- end: `0x14005f378`
- name: `GreGetDCObject`
- size: `1016`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1400d1c28`

## callees

- `0x14005ef80`
- `0x1400604f0`
- `0x1400781e8`
- `0x14007eef8`
- `0x140080590`
- `0x140164228`
- `0x140303af4`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14005f056`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14005f056`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005efc2`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005f21f`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005efc2`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x14005f21f`
- `win32kbase!HmgPentryFromPobj` at `0x14005f07e`
- `win32kbase!HmgPentryFromPobj` at `0x14005f07e`
- `win32kbase!PushThreadGuardedObject` at `0x14005efff`
- `win32kbase!PushThreadGuardedObject` at `0x14005f109`
- `win32kbase!PushThreadGuardedObject` at `0x14005efff`
- `win32kbase!PushThreadGuardedObject` at `0x14005f109`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005f09d`
- `win32kbase!?GetUserAttr@DCOBJ@@AEAAPEAU_DC_ATTR@@XZ` at `0x14005f09d`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005f331`
- `win32kbase!?GreEncodeUserModePointer@@YAPEAXPEAX@Z` at `0x14005f331`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14005f0b6`
- `win32kbase!?SaveAttributes@DC@@QEAAHPEAU_DC_ATTR@@@Z` at `0x14005f0b6`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14005f2ad`
- `win32kbase!?GrepAuditBehaviorRestrictionViolations@@YA_NW4GreBehaviorRestriction@@@Z` at `0x14005f2ad`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14005ef9c`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14005f299`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14005ef9c`
- `win32kbase!?GrepGetCurrentProcessBehaviorRestriction@@YA?AW4GreBehaviorRestriction@@XZ` at `0x14005f299`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14005f019`
- `win32kbase!?HmgLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z` at `0x14005f019`
- `win32kbase!?vLockNoDrawing@DEVLOCKOBJ@@QEAAXAEAVXDCOBJ@@@Z` at `0x14005f213`
- `win32kbase!?vLockNoDrawing@DEVLOCKOBJ@@QEAAXAEAVXDCOBJ@@@Z` at `0x14005f213`
- `win32kbase!GreDCSelectBrush` at `0x14005f173`
- `win32kbase!GreDCSelectBrush` at `0x14005f173`
- `win32kbase!GreDCSelectPen` at `0x14005f19b`
- `win32kbase!GreDCSelectPen` at `0x14005f19b`
- `win32kbase!GreGetStockObject` at `0x14005f2dd`
- `win32kbase!GreGetStockObject` at `0x14005f2dd`

## pseudocode

```c

```

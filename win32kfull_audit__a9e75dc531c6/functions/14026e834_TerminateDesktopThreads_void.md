# TerminateDesktopThreads(void)

- ea: `0x14026e834`
- end: `0x14026f085`
- name: `?TerminateDesktopThreads@@YAXXZ`
- size: `2129`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1402a9cbc`

## callees

- `0x1400dd43c`
- `0x1401fd034`
- `0x14026e834`
- `0x1402aae2c`

## import_xrefs

- `ntoskrnl!KeWaitForMultipleObjects` at `0x14026ed79`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14026ed79`
- `ntoskrnl!KeSetEvent` at `0x14026e996`
- `ntoskrnl!KeSetEvent` at `0x14026ebce`
- `ntoskrnl!KeSetEvent` at `0x14026e996`
- `ntoskrnl!KeSetEvent` at `0x14026ebce`
- `ntoskrnl!ObfReferenceObject` at `0x14026e8dd`
- `ntoskrnl!ObfReferenceObject` at `0x14026ea8c`
- `ntoskrnl!ObfReferenceObject` at `0x14026e8dd`
- `ntoskrnl!ObfReferenceObject` at `0x14026ea8c`
- `ntoskrnl!ObfDereferenceObject` at `0x14026f043`
- `ntoskrnl!ObfDereferenceObject` at `0x14026f043`
- `win32kbase!?CleanupInputDestHwndRefsForDesktopThreadExit@CTouchProcessor@@QEAAXXZ` at `0x14026e885`
- `win32kbase!?CleanupInputDestHwndRefsForDesktopThreadExit@CTouchProcessor@@QEAAXXZ` at `0x14026e885`
- `win32kbase!EnterCrit` at `0x14026ed8c`
- `win32kbase!EnterCrit` at `0x14026ed8c`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14026ed3c`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14026ed3c`
- `win32kbase!HMAssignmentUnlock` at `0x14026ea68`
- `win32kbase!HMAssignmentUnlock` at `0x14026ea68`
- `WIN32K!W32GetUserSessionState` at `0x14026e85c`
- `WIN32K!W32GetUserSessionState` at `0x14026e872`
- `WIN32K!W32GetUserSessionState` at `0x14026e891`
- `WIN32K!W32GetUserSessionState` at `0x14026e8a0`
- `WIN32K!W32GetUserSessionState` at `0x14026e92c`
- `WIN32K!W32GetUserSessionState` at `0x14026e9d9`
- `WIN32K!W32GetUserSessionState` at `0x14026ea37`
- `WIN32K!W32GetUserSessionState` at `0x14026eacd`
- `WIN32K!W32GetUserSessionState` at `0x14026eb63`
- `WIN32K!W32GetUserSessionState` at `0x14026ec6d`
- `WIN32K!W32GetUserSessionState` at `0x14026ece8`
- `WIN32K!W32GetUserSessionState` at `0x14026ede8`
- `WIN32K!W32GetUserSessionState` at `0x14026ee30`
- `WIN32K!W32GetUserSessionState` at `0x14026eea4`
- `WIN32K!W32GetUserSessionState` at `0x14026ef55`
- `WIN32K!W32GetUserSessionState` at `0x14026eff4`
- `WIN32K!W32GetUserSessionState` at `0x14026f057`
- `WIN32K!W32GetUserSessionState` at `0x14026e85c`
- `WIN32K!W32GetUserSessionState` at `0x14026e872`
- `WIN32K!W32GetUserSessionState` at `0x14026e891`
- `WIN32K!W32GetUserSessionState` at `0x14026e8a0`
- `WIN32K!W32GetUserSessionState` at `0x14026e92c`
- `WIN32K!W32GetUserSessionState` at `0x14026e9d9`
- `WIN32K!W32GetUserSessionState` at `0x14026ea37`
- `WIN32K!W32GetUserSessionState` at `0x14026eacd`
- `WIN32K!W32GetUserSessionState` at `0x14026eb63`
- `WIN32K!W32GetUserSessionState` at `0x14026ec6d`
- `WIN32K!W32GetUserSessionState` at `0x14026ece8`
- `WIN32K!W32GetUserSessionState` at `0x14026ede8`
- `WIN32K!W32GetUserSessionState` at `0x14026ee30`
- `WIN32K!W32GetUserSessionState` at `0x14026eea4`
- `WIN32K!W32GetUserSessionState` at `0x14026ef55`
- `WIN32K!W32GetUserSessionState` at `0x14026eff4`
- `WIN32K!W32GetUserSessionState` at `0x14026f057`

## pseudocode

```c

```

# TerminateDesktopThreads(void)

- ea: `0x14026b364`
- end: `0x14026bbb5`
- name: `?TerminateDesktopThreads@@YAXXZ`
- size: `2129`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1402a78dc`

## callees

- `0x1400b71ac`
- `0x1401fba84`
- `0x14026b364`
- `0x1402a8a4c`

## import_xrefs

- `ntoskrnl!KeWaitForMultipleObjects` at `0x14026b8a9`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14026b8a9`
- `ntoskrnl!KeSetEvent` at `0x14026b4c6`
- `ntoskrnl!KeSetEvent` at `0x14026b6fe`
- `ntoskrnl!KeSetEvent` at `0x14026b4c6`
- `ntoskrnl!KeSetEvent` at `0x14026b6fe`
- `ntoskrnl!ObfReferenceObject` at `0x14026b40d`
- `ntoskrnl!ObfReferenceObject` at `0x14026b5bc`
- `ntoskrnl!ObfReferenceObject` at `0x14026b40d`
- `ntoskrnl!ObfReferenceObject` at `0x14026b5bc`
- `ntoskrnl!ObfDereferenceObject` at `0x14026bb73`
- `ntoskrnl!ObfDereferenceObject` at `0x14026bb73`
- `win32kbase!?CleanupInputDestHwndRefsForDesktopThreadExit@CTouchProcessor@@QEAAXXZ` at `0x14026b3b5`
- `win32kbase!?CleanupInputDestHwndRefsForDesktopThreadExit@CTouchProcessor@@QEAAXXZ` at `0x14026b3b5`
- `win32kbase!EnterCrit` at `0x14026b8bc`
- `win32kbase!EnterCrit` at `0x14026b8bc`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14026b86c`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x14026b86c`
- `win32kbase!HMAssignmentUnlock` at `0x14026b598`
- `win32kbase!HMAssignmentUnlock` at `0x14026b598`
- `WIN32K!W32GetUserSessionState` at `0x14026b38c`
- `WIN32K!W32GetUserSessionState` at `0x14026b3a2`
- `WIN32K!W32GetUserSessionState` at `0x14026b3c1`
- `WIN32K!W32GetUserSessionState` at `0x14026b3d0`
- `WIN32K!W32GetUserSessionState` at `0x14026b45c`
- `WIN32K!W32GetUserSessionState` at `0x14026b509`
- `WIN32K!W32GetUserSessionState` at `0x14026b567`
- `WIN32K!W32GetUserSessionState` at `0x14026b5fd`
- `WIN32K!W32GetUserSessionState` at `0x14026b693`
- `WIN32K!W32GetUserSessionState` at `0x14026b79d`
- `WIN32K!W32GetUserSessionState` at `0x14026b818`
- `WIN32K!W32GetUserSessionState` at `0x14026b918`
- `WIN32K!W32GetUserSessionState` at `0x14026b960`
- `WIN32K!W32GetUserSessionState` at `0x14026b9d4`
- `WIN32K!W32GetUserSessionState` at `0x14026ba85`
- `WIN32K!W32GetUserSessionState` at `0x14026bb24`
- `WIN32K!W32GetUserSessionState` at `0x14026bb87`
- `WIN32K!W32GetUserSessionState` at `0x14026b38c`
- `WIN32K!W32GetUserSessionState` at `0x14026b3a2`
- `WIN32K!W32GetUserSessionState` at `0x14026b3c1`
- `WIN32K!W32GetUserSessionState` at `0x14026b3d0`
- `WIN32K!W32GetUserSessionState` at `0x14026b45c`
- `WIN32K!W32GetUserSessionState` at `0x14026b509`
- `WIN32K!W32GetUserSessionState` at `0x14026b567`
- `WIN32K!W32GetUserSessionState` at `0x14026b5fd`
- `WIN32K!W32GetUserSessionState` at `0x14026b693`
- `WIN32K!W32GetUserSessionState` at `0x14026b79d`
- `WIN32K!W32GetUserSessionState` at `0x14026b818`
- `WIN32K!W32GetUserSessionState` at `0x14026b918`
- `WIN32K!W32GetUserSessionState` at `0x14026b960`
- `WIN32K!W32GetUserSessionState` at `0x14026b9d4`
- `WIN32K!W32GetUserSessionState` at `0x14026ba85`
- `WIN32K!W32GetUserSessionState` at `0x14026bb24`
- `WIN32K!W32GetUserSessionState` at `0x14026bb87`

## pseudocode

```c

```

# NtUserGrantJobUIRestrictionException

- ea: `0x1402bb0a0`
- end: `0x1402bb447`
- name: `NtUserGrantJobUIRestrictionException`
- size: `935`
- prototype: `__int64 __fastcall(HANDLE Handle, HANDLE)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400b5444`
- `0x1400b71ac`
- `0x1400c2a10`
- `0x1400ec110`
- `0x140198928`
- `0x1402b64a8`
- `0x1402bb0a0`

## import_xrefs

- `ntoskrnl!PsJobType` at `0x1402bb12c`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x1402bb17a`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x1402bb31d`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x1402bb17a`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x1402bb31d`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1402bb3e0`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1402bb3fb`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1402bb3e0`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1402bb3fb`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1402bb21d`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1402bb3c0`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1402bb21d`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1402bb3c0`
- `ntoskrnl!PsProcessType` at `0x1402bb2e4`
- `ntoskrnl!KeBugCheckEx` at `0x1402bb43a`
- `ntoskrnl!KeBugCheckEx` at `0x1402bb43a`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1402bb120`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1402bb120`
- `ntoskrnl!PsGetJobUIRestrictionsClass` at `0x1402bb23d`
- `ntoskrnl!PsGetJobUIRestrictionsClass` at `0x1402bb23d`
- `win32kbase!EnterCrit` at `0x1402bb0f1`
- `win32kbase!EnterCrit` at `0x1402bb0f1`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402bb411`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402bb411`
- `WIN32K!W32GetUserSessionState` at `0x1402bb0fd`
- `WIN32K!W32GetUserSessionState` at `0x1402bb1cf`
- `WIN32K!W32GetUserSessionState` at `0x1402bb292`
- `WIN32K!W32GetUserSessionState` at `0x1402bb372`
- `WIN32K!W32GetUserSessionState` at `0x1402bb0fd`
- `WIN32K!W32GetUserSessionState` at `0x1402bb1cf`
- `WIN32K!W32GetUserSessionState` at `0x1402bb292`
- `WIN32K!W32GetUserSessionState` at `0x1402bb372`

## pseudocode

```c

```

# NtUserGrantJobUIRestrictionException

- ea: `0x1402bcf30`
- end: `0x1402bd2d7`
- name: `NtUserGrantJobUIRestrictionException`
- size: `935`
- prototype: `__int64 __fastcall(HANDLE Handle, HANDLE, int)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140005a18`
- `0x1400db6d4`
- `0x1400dd43c`
- `0x1400e8c20`
- `0x14017cc14`
- `0x1402b81b8`
- `0x1402bcf30`

## import_xrefs

- `ntoskrnl!PsJobType` at `0x1402bcfbc`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x1402bd00a`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x1402bd1ad`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x1402bd00a`
- `ntoskrnl!ObReferenceObjectByHandleWithTag` at `0x1402bd1ad`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1402bd270`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1402bd28b`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1402bd270`
- `ntoskrnl!ObfDereferenceObjectWithTag` at `0x1402bd28b`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1402bd0ad`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1402bd250`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1402bd0ad`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1402bd250`
- `ntoskrnl!PsProcessType` at `0x1402bd174`
- `ntoskrnl!KeBugCheckEx` at `0x1402bd2ca`
- `ntoskrnl!KeBugCheckEx` at `0x1402bd2ca`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1402bcfb0`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1402bcfb0`
- `ntoskrnl!PsGetJobUIRestrictionsClass` at `0x1402bd0cd`
- `ntoskrnl!PsGetJobUIRestrictionsClass` at `0x1402bd0cd`
- `win32kbase!EnterCrit` at `0x1402bcf81`
- `win32kbase!EnterCrit` at `0x1402bcf81`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402bd2a1`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402bd2a1`
- `WIN32K!W32GetUserSessionState` at `0x1402bcf8d`
- `WIN32K!W32GetUserSessionState` at `0x1402bd05f`
- `WIN32K!W32GetUserSessionState` at `0x1402bd122`
- `WIN32K!W32GetUserSessionState` at `0x1402bd202`
- `WIN32K!W32GetUserSessionState` at `0x1402bcf8d`
- `WIN32K!W32GetUserSessionState` at `0x1402bd05f`
- `WIN32K!W32GetUserSessionState` at `0x1402bd122`
- `WIN32K!W32GetUserSessionState` at `0x1402bd202`

## pseudocode

```c

```

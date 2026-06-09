# NtUserSetProcessWin32Capabilities

- ea: `0x1402c09d0`
- end: `0x1402c0f13`
- name: `NtUserSetProcessWin32Capabilities`
- size: `1347`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation`

## callees

- `0x1400381a8`
- `0x1400b71ac`
- `0x1400c11d8`
- `0x1400c2a10`
- `0x140198928`
- `0x1402a4d38`
- `0x1402b0d40`
- `0x1402c09d0`

## import_xrefs

- `ntoskrnl!RtlNtStatusToDosError` at `0x1402c0beb`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1402c0cb6`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1402c0beb`
- `ntoskrnl!RtlNtStatusToDosError` at `0x1402c0cb6`
- `ntoskrnl!PsProcessType` at `0x1402c0af0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402c0b23`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1402c0b23`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1402c0c03`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1402c0c03`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c0ec1`
- `ntoskrnl!ObfDereferenceObject` at `0x1402c0ec1`
- `win32kbase!HasTcbPrivilege` at `0x1402c09f1`
- `win32kbase!HasTcbPrivilege` at `0x1402c09f1`
- `win32kbase!EnterCrit` at `0x1402c0a16`
- `win32kbase!EnterCrit` at `0x1402c0a16`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402c0ef0`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1402c0ef0`
- `win32kbase!Win32AllocPoolZInit` at `0x1402c0a3b`
- `win32kbase!Win32AllocPoolZInit` at `0x1402c0a3b`
- `win32kbase!Win32FreePool` at `0x1402c0ed7`
- `win32kbase!Win32FreePool` at `0x1402c0ed7`
- `WIN32K!W32GetUserSessionState` at `0x1402c0b8c`
- `WIN32K!W32GetUserSessionState` at `0x1402c0c61`
- `WIN32K!W32GetUserSessionState` at `0x1402c0d2b`
- `WIN32K!W32GetUserSessionState` at `0x1402c0e08`
- `WIN32K!W32GetUserSessionState` at `0x1402c0b8c`
- `WIN32K!W32GetUserSessionState` at `0x1402c0c61`
- `WIN32K!W32GetUserSessionState` at `0x1402c0d2b`
- `WIN32K!W32GetUserSessionState` at `0x1402c0e08`

## pseudocode

```c

```

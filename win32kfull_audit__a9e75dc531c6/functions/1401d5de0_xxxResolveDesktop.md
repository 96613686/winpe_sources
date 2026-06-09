# xxxResolveDesktop

- ea: `0x1401d5de0`
- end: `0x1401d6aa7`
- name: `xxxResolveDesktop`
- size: `3271`
- prototype: `NTSTATUS __fastcall(void *, UNICODE_STRING *, HANDLE *, int, HANDLE *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task`

## callees

- `0x1400330e0`
- `0x140033b58`
- `0x1400b5ffc`
- `0x1400b604c`
- `0x1400b66fc`
- `0x1401d5de0`
- `0x1401d6ab0`
- `0x1401d6b1c`
- `0x1401d6ff0`
- `0x140200e50`
- `0x140209220`
- `0x140342fa0`

## import_xrefs

- `ntoskrnl!ZwDuplicateObject` at `0x1401d64b3`
- `ntoskrnl!ZwDuplicateObject` at `0x1401d690b`
- `ntoskrnl!ZwDuplicateObject` at `0x1401d64b3`
- `ntoskrnl!ZwDuplicateObject` at `0x1401d690b`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x1401d65ef`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x1401d6871`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x1401d65ef`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x1401d6871`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x1401d61cb`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x1401d6a3d`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x1401d61cb`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x1401d6a3d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1401d60d9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1401d6195`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1401d659a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1401d60d9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1401d6195`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1401d659a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1401d60a8`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1401d60c0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1401d6164`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1401d617c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1401d6569`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1401d6581`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1401d60a8`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1401d60c0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1401d6164`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1401d617c`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1401d6569`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1401d6581`
- `ntoskrnl!ObFindHandleForObject` at `0x1401d6461`
- `ntoskrnl!ObFindHandleForObject` at `0x1401d68b5`
- `ntoskrnl!ObFindHandleForObject` at `0x1401d6461`
- `ntoskrnl!ObFindHandleForObject` at `0x1401d68b5`
- `ntoskrnl!PsProcessType` at `0x1401d5ea1`
- `ntoskrnl!ExDesktopObjectType` at `0x1401d666a`
- `ntoskrnl!ExDesktopObjectType` at `0x1401d68a6`
- `ntoskrnl!ExDesktopObjectType` at `0x1401d6962`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d5eb0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d67b5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d696e`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d5eb0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d67b5`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1401d696e`
- `ntoskrnl!ObCloseHandle` at `0x1401d62fa`
- `ntoskrnl!ObCloseHandle` at `0x1401d66a5`
- `ntoskrnl!ObCloseHandle` at `0x1401d62fa`
- `ntoskrnl!ObCloseHandle` at `0x1401d66a5`
- `ntoskrnl!ExWindowStationObjectType` at `0x1401d6452`
- `ntoskrnl!ExWindowStationObjectType` at `0x1401d6628`
- `ntoskrnl!ExWindowStationObjectType` at `0x1401d67a9`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401d5f60`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401d6475`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401d68c9`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401d5f60`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401d6475`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401d68c9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401d6344`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401d6344`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d6010`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d6088`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d6769`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d6010`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d6088`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401d6769`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401d6649`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401d668b`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401d6649`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1401d668b`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d5f90`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d6414`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d6603`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d6807`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d6880`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d69eb`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d5f90`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d6414`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d6603`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d6807`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d6880`
- `ntoskrnl!ObfDereferenceObject` at `0x1401d69eb`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1401d5f00`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1401d5f00`
- `win32kbase!GetProcessLuid` at `0x1401d6716`
- `win32kbase!GetProcessLuid` at `0x1401d6716`
- `WIN32K!W32GetUserSessionState` at `0x1401d5fe1`
- `WIN32K!W32GetUserSessionState` at `0x1401d60e5`
- `WIN32K!W32GetUserSessionState` at `0x1401d62c0`
- `WIN32K!W32GetUserSessionState` at `0x1401d5fe1`
- `WIN32K!W32GetUserSessionState` at `0x1401d60e5`
- `WIN32K!W32GetUserSessionState` at `0x1401d62c0`

## string_xrefs

- `0x1401d6740`: `Service-0x%x-%x$`

## pseudocode

```c

```

# NtUserProcessConnect

- ea: `0x1400c9d00`
- end: `0x1400ca330`
- name: `NtUserProcessConnect`
- size: `1584`
- prototype: `__int64 __fastcall(HANDLE Handle, size_t Size)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400c9d00`
- `0x1400ca338`
- `0x1400dd43c`
- `0x140342fa0`
- `0x140343080`
- `0x140343200`
- `0x140343500`

## import_xrefs

- `ntoskrnl!PsIsProtectedProcessLight` at `0x1400ca0cc`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x1400ca0cc`
- `ntoskrnl!PsIsProtectedProcess` at `0x1400c9f3b`
- `ntoskrnl!PsIsProtectedProcess` at `0x1400c9f3b`
- `ntoskrnl!PsReleaseProcessExitSynchronization` at `0x1400c9ffc`
- `ntoskrnl!PsReleaseProcessExitSynchronization` at `0x1400c9ffc`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400c9fed`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400c9fed`
- `ntoskrnl!KeStackAttachProcess` at `0x1400ca138`
- `ntoskrnl!KeStackAttachProcess` at `0x1400ca138`
- `ntoskrnl!PsAcquireProcessExitSynchronization` at `0x1400ca0f4`
- `ntoskrnl!PsAcquireProcessExitSynchronization` at `0x1400ca0f4`
- `ntoskrnl!PsProcessType` at `0x1400c9ef7`
- `ntoskrnl!ProbeForWrite` at `0x1400c9e80`
- `ntoskrnl!ProbeForWrite` at `0x1400ca22f`
- `ntoskrnl!ProbeForWrite` at `0x1400c9e80`
- `ntoskrnl!ProbeForWrite` at `0x1400ca22f`
- `ntoskrnl!ProbeForRead` at `0x1400ca1b8`
- `ntoskrnl!ProbeForRead` at `0x1400ca1b8`
- `ntoskrnl!PsGetProcessPeb` at `0x1400ca11c`
- `ntoskrnl!PsGetProcessPeb` at `0x1400ca11c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400c9f06`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400c9f06`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400c9e18`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400c9f27`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400c9e18`
- `ntoskrnl!PsGetCurrentProcess` at `0x1400c9f27`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ca00b`
- `ntoskrnl!ObfDereferenceObject` at `0x1400ca00b`
- `win32kbase!EnterCrit` at `0x1400c9f67`
- `win32kbase!EnterCrit` at `0x1400c9f67`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400c9f85`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x1400c9f85`
- `WIN32K!W32GetWin32kFullApiSetTable` at `0x1400c9e39`
- `WIN32K!W32GetWin32kFullApiSetTable` at `0x1400c9ea1`
- `WIN32K!W32GetWin32kFullApiSetTable` at `0x1400c9e39`
- `WIN32K!W32GetWin32kFullApiSetTable` at `0x1400c9ea1`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400c9e08`
- `WIN32K!W32GetUserGdiSessionState` at `0x1400c9e08`
- `WIN32K!W32GetUserSessionState` at `0x1400c9dae`
- `WIN32K!W32GetUserSessionState` at `0x1400ca046`
- `WIN32K!W32GetUserSessionState` at `0x1400c9dae`
- `WIN32K!W32GetUserSessionState` at `0x1400ca046`

## pseudocode

```c

```

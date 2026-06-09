# NtUserProcessConnect

- ea: `0x140007000`
- end: `0x140007630`
- name: `NtUserProcessConnect`
- size: `1584`
- prototype: `__int64 __fastcall(HANDLE Handle, size_t Size)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x140007000`
- `0x140007638`
- `0x1400b71ac`
- `0x140341ff0`
- `0x1403420d0`
- `0x140342240`
- `0x140342540`

## import_xrefs

- `ntoskrnl!PsIsProtectedProcessLight` at `0x1400073cc`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x1400073cc`
- `ntoskrnl!PsIsProtectedProcess` at `0x14000723b`
- `ntoskrnl!PsIsProtectedProcess` at `0x14000723b`
- `ntoskrnl!PsReleaseProcessExitSynchronization` at `0x1400072fc`
- `ntoskrnl!PsReleaseProcessExitSynchronization` at `0x1400072fc`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400072ed`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400072ed`
- `ntoskrnl!KeStackAttachProcess` at `0x140007438`
- `ntoskrnl!KeStackAttachProcess` at `0x140007438`
- `ntoskrnl!PsAcquireProcessExitSynchronization` at `0x1400073f4`
- `ntoskrnl!PsAcquireProcessExitSynchronization` at `0x1400073f4`
- `ntoskrnl!PsProcessType` at `0x1400071f7`
- `ntoskrnl!ProbeForWrite` at `0x140007180`
- `ntoskrnl!ProbeForWrite` at `0x14000752f`
- `ntoskrnl!ProbeForWrite` at `0x140007180`
- `ntoskrnl!ProbeForWrite` at `0x14000752f`
- `ntoskrnl!ProbeForRead` at `0x1400074b8`
- `ntoskrnl!ProbeForRead` at `0x1400074b8`
- `ntoskrnl!PsGetProcessPeb` at `0x14000741c`
- `ntoskrnl!PsGetProcessPeb` at `0x14000741c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140007206`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140007206`
- `ntoskrnl!PsGetCurrentProcess` at `0x140007118`
- `ntoskrnl!PsGetCurrentProcess` at `0x140007227`
- `ntoskrnl!PsGetCurrentProcess` at `0x140007118`
- `ntoskrnl!PsGetCurrentProcess` at `0x140007227`
- `ntoskrnl!ObfDereferenceObject` at `0x14000730b`
- `ntoskrnl!ObfDereferenceObject` at `0x14000730b`
- `win32kbase!EnterCrit` at `0x140007267`
- `win32kbase!EnterCrit` at `0x140007267`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140007285`
- `win32kbase!UserSessionSwitchLeaveCrit` at `0x140007285`
- `WIN32K!W32GetWin32kFullApiSetTable` at `0x140007139`
- `WIN32K!W32GetWin32kFullApiSetTable` at `0x1400071a1`
- `WIN32K!W32GetWin32kFullApiSetTable` at `0x140007139`
- `WIN32K!W32GetWin32kFullApiSetTable` at `0x1400071a1`
- `WIN32K!W32GetUserGdiSessionState` at `0x140007108`
- `WIN32K!W32GetUserGdiSessionState` at `0x140007108`
- `WIN32K!W32GetUserSessionState` at `0x1400070ae`
- `WIN32K!W32GetUserSessionState` at `0x140007346`
- `WIN32K!W32GetUserSessionState` at `0x1400070ae`
- `WIN32K!W32GetUserSessionState` at `0x140007346`

## pseudocode

```c

```

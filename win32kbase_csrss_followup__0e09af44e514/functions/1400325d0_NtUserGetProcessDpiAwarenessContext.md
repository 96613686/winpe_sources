# NtUserGetProcessDpiAwarenessContext

- ea: `0x1400325d0`
- end: `0x14003276a`
- name: `NtUserGetProcessDpiAwarenessContext`
- size: `410`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14001bdf0`
- `0x14001c420`
- `0x140031bf4`
- `0x1400325d0`
- `0x140033268`
- `0x14006cdb0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140032600`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140032600`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140032623`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140032643`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140032623`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x140032643`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400326e5`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x1400326e5`
- `ntoskrnl!PsProcessType` at `0x14003269c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400326cd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400326cd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400325f1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x1400325f1`
- `ntoskrnl!ObfDereferenceObject` at `0x140032678`
- `ntoskrnl!ObfDereferenceObject` at `0x140032678`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400326ff`
- `ntoskrnl!PsGetProcessWin32Process` at `0x1400326ff`
- `WIN32K!W32GetUserSessionState` at `0x1400325e2`
- `WIN32K!W32GetUserSessionState` at `0x1400325e2`

## pseudocode

```c

```

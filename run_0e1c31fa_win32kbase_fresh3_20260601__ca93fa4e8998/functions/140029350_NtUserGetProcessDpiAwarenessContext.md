# NtUserGetProcessDpiAwarenessContext

- ea: `0x140029350`
- end: `0x1400294ea`
- name: `NtUserGetProcessDpiAwarenessContext`
- size: `410`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140012c80`
- `0x1400132b0`
- `0x140028974`
- `0x140029350`
- `0x140029fe8`
- `0x14006bc10`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140029380`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140029380`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400293a3`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400293c3`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400293a3`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400293c3`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140029465`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140029465`
- `ntoskrnl!PsProcessType` at `0x14002941c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002944d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002944d`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140029371`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140029371`
- `ntoskrnl!ObfDereferenceObject` at `0x1400293f8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400293f8`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14002947f`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14002947f`
- `WIN32K!W32GetUserSessionState` at `0x140029362`
- `WIN32K!W32GetUserSessionState` at `0x140029362`

## pseudocode

```c

```

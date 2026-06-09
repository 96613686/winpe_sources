# NtUserGetProcessDpiAwarenessContext

- ea: `0x14006f3d0`
- end: `0x14006f56a`
- name: `NtUserGetProcessDpiAwarenessContext`
- size: `410`
- prototype: `__int64 __fastcall(char *Handle, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140029710`
- `0x140029d40`
- `0x1400371c0`
- `0x1400441e0`
- `0x14006f3d0`
- `0x1400700d8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14006f400`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006f400`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14006f423`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14006f443`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14006f423`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14006f443`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14006f4e5`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14006f4e5`
- `ntoskrnl!PsProcessType` at `0x14006f49c`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006f4cd`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14006f4cd`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14006f3f1`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14006f3f1`
- `ntoskrnl!ObfDereferenceObject` at `0x14006f478`
- `ntoskrnl!ObfDereferenceObject` at `0x14006f478`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14006f4ff`
- `ntoskrnl!PsGetProcessWin32Process` at `0x14006f4ff`
- `WIN32K!W32GetUserSessionState` at `0x14006f3e2`
- `WIN32K!W32GetUserSessionState` at `0x14006f3e2`

## pseudocode

```c

```

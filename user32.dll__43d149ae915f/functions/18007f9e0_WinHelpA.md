# WinHelpA

- ea: `0x18007f9e0`
- end: `0x18007fe8f`
- name: `WinHelpA`
- size: `1199`
- prototype: `BOOL __stdcall(HWND hWndMain, LPCSTR lpszHelp, UINT uCommand, ULONG_PTR dwData)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800673d0`

## callees

- `0x18000d210`
- `0x18000e760`
- `0x180010980`
- `0x1800111f4`
- `0x180016d50`
- `0x180017b3c`
- `0x180029f40`
- `0x18002a8ec`
- `0x18002aa38`
- `0x18002aa8c`
- `0x1800309a0`
- `0x1800312fc`
- `0x180034c90`
- `0x180067790`
- `0x180070674`
- `0x18007f6c0`
- `0x18007f97c`
- `0x18007f9e0`

## import_xrefs

- `win32u!NtUserGetCursorPos` at `0x18007fac9`
- `win32u!NtUserGetCursorPos` at `0x18007fac9`
- `win32u!NtUserDestroyMenu` at `0x18007fd60`
- `win32u!NtUserDestroyMenu` at `0x18007fd60`
- `ntdll!RtlSetLastWin32Error` at `0x18007fa4f`
- `ntdll!RtlSetLastWin32Error` at `0x18007fa4f`
- `ntdll!RtlFreeHeap` at `0x18007fdd3`
- `ntdll!RtlFreeHeap` at `0x18007fe72`
- `ntdll!RtlFreeHeap` at `0x18007fdd3`
- `ntdll!RtlFreeHeap` at `0x18007fe72`

## pseudocode

```c

```

# GetWindowLongPtrW

- ea: `0x18000bd00`
- end: `0x18000be2e`
- name: `GetWindowLongPtrW`
- size: `302`
- prototype: `LONG_PTR __stdcall(HWND hWnd, int nIndex)`
- caller_count: `20`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180019b90`
- `0x180019c04`
- `0x180045fc0`
- `0x180046f30`
- `0x180047800`
- `0x18004b590`
- `0x18004e210`
- `0x18005c9a0`
- `0x18005e60c`
- `0x180060370`
- `0x180061988`
- `0x180073ab0`
- `0x180076dd0`
- `0x180077370`
- `0x180077640`
- `0x1800782a0`
- `0x180088568`
- `0x1800889f8`
- `0x180088c9c`
- `0x180091490`

## callees

- `0x18000bd00`
- `0x18000be40`
- `0x18000d9b0`

## import_xrefs

- `win32u!NtUserMapDesktopObject` at `0x18000be19`
- `win32u!NtUserMapDesktopObject` at `0x18000be19`
- `win32u!NtUserValidateHandleSecure` at `0x18000bdfa`
- `win32u!NtUserValidateHandleSecure` at `0x18000bdfa`
- `ntdll!RtlSetLastWin32Error` at `0x18000bdd4`
- `ntdll!RtlSetLastWin32Error` at `0x18000be09`
- `ntdll!RtlSetLastWin32Error` at `0x18000bdd4`
- `ntdll!RtlSetLastWin32Error` at `0x18000be09`

## pseudocode

```c

```

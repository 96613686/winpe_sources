# GetWindowInfo

- ea: `0x18005a230`
- end: `0x18005a447`
- name: `GetWindowInfo`
- size: `535`
- prototype: `BOOL __stdcall(HWND hwnd, PWINDOWINFO pwi)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1800073b4`
- `0x18000d210`
- `0x18005a230`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserTransformRect` at `0x18005a3e4`
- `win32u!NtUserTransformRect` at `0x18005a3ff`
- `win32u!NtUserTransformRect` at `0x18005a3e4`
- `win32u!NtUserTransformRect` at `0x18005a3ff`
- `win32u!NtUserGetThreadState` at `0x18005a433`
- `win32u!NtUserGetThreadState` at `0x18005a433`
- `ntdll!RtlSetLastWin32Error` at `0x18005a355`
- `ntdll!RtlSetLastWin32Error` at `0x18005a423`
- `ntdll!RtlSetLastWin32Error` at `0x18005a355`
- `ntdll!RtlSetLastWin32Error` at `0x18005a423`

## pseudocode

```c

```

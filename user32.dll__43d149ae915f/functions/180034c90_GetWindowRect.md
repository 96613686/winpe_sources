# GetWindowRect

- ea: `0x180034c90`
- end: `0x180034e2d`
- name: `GetWindowRect`
- size: `413`
- prototype: `BOOL __stdcall(HWND hWnd, LPRECT lpRect)`
- caller_count: `7`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008ab0`
- `0x1800331ec`
- `0x180040b90`
- `0x18007aafc`
- `0x18007f9e0`
- `0x180086ab0`
- `0x180089550`

## callees

- `0x18000d210`
- `0x180014a4c`
- `0x180014c10`
- `0x180034c90`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserTransformRect` at `0x180034dd3`
- `win32u!NtUserTransformRect` at `0x180034dd3`
- `win32u!NtUserGetThreadState` at `0x180034e19`
- `win32u!NtUserGetThreadState` at `0x180034e19`
- `ntdll!RtlSetLastWin32Error` at `0x180034d67`
- `ntdll!RtlSetLastWin32Error` at `0x180034d67`

## pseudocode

```c

```

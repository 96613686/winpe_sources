# IsDeviceLockable

- ea: `0x18000e1e8`
- end: `0x18000e499`
- name: `IsDeviceLockable`
- size: `689`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800113d0`

## callees

- `0x1800083e4`
- `0x18000e1e8`
- `0x180014c30`
- `0x180072e08`
- `0x180072f14`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18000e2bc`
- `KERNEL32!CreateFileW` at `0x18000e2bc`
- `KERNEL32!GetLastError` at `0x18000e2d6`
- `KERNEL32!GetLastError` at `0x18000e359`
- `KERNEL32!GetLastError` at `0x18000e2d6`
- `KERNEL32!GetLastError` at `0x18000e359`
- `KERNEL32!CloseHandle` at `0x18000e457`
- `KERNEL32!CloseHandle` at `0x18000e457`
- `KERNEL32!DeviceIoControl` at `0x18000e349`
- `KERNEL32!DeviceIoControl` at `0x18000e3dd`
- `KERNEL32!DeviceIoControl` at `0x18000e349`
- `KERNEL32!DeviceIoControl` at `0x18000e3dd`

## pseudocode

```c

```

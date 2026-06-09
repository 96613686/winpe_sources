# IsDeviceLockable

- ea: `0x18000dd30`
- end: `0x18000dfbc`
- name: `IsDeviceLockable`
- size: `652`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180010cc0`

## callees

- `0x180008240`
- `0x18000dd30`
- `0x180014394`
- `0x18006fe84`
- `0x18006ff8c`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18000de04`
- `KERNEL32!CreateFileW` at `0x18000de04`
- `KERNEL32!GetLastError` at `0x18000de18`
- `KERNEL32!GetLastError` at `0x18000de8f`
- `KERNEL32!GetLastError` at `0x18000de18`
- `KERNEL32!GetLastError` at `0x18000de8f`
- `KERNEL32!CloseHandle` at `0x18000df81`
- `KERNEL32!CloseHandle` at `0x18000df81`
- `KERNEL32!DeviceIoControl` at `0x18000de85`
- `KERNEL32!DeviceIoControl` at `0x18000df0d`
- `KERNEL32!DeviceIoControl` at `0x18000de85`
- `KERNEL32!DeviceIoControl` at `0x18000df0d`

## pseudocode

```c

```

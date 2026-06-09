# BlbIsDeviceLockable(ushort *,uchar *)

- ea: `0x1401166bc`
- end: `0x14011699f`
- name: `?BlbIsDeviceLockable@@YAJPEAGPEAE@Z`
- size: `739`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x1401060f4`
- `0x1401061f8`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x140014200`
- `0x140014260`
- `0x140088ba4`
- `0x1401166bc`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14011679b`
- `KERNEL32!CreateFileW` at `0x14011679b`
- `KERNEL32!CloseHandle` at `0x140116946`
- `KERNEL32!CloseHandle` at `0x140116946`
- `KERNEL32!GetLastError` at `0x1401167aa`
- `KERNEL32!GetLastError` at `0x14011686d`
- `KERNEL32!GetLastError` at `0x1401167aa`
- `KERNEL32!GetLastError` at `0x14011686d`
- `KERNEL32!DeviceIoControl` at `0x14011683f`
- `KERNEL32!DeviceIoControl` at `0x1401168d3`
- `KERNEL32!DeviceIoControl` at `0x14011683f`
- `KERNEL32!DeviceIoControl` at `0x1401168d3`
- `ole32!CoTaskMemFree` at `0x14011695b`
- `ole32!CoTaskMemFree` at `0x14011695b`

## pseudocode

```c

```

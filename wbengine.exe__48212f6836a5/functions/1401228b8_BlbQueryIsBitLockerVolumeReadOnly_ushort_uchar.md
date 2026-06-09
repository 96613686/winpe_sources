# BlbQueryIsBitLockerVolumeReadOnly(ushort *,uchar *)

- ea: `0x1401228b8`
- end: `0x140122b50`
- name: `?BlbQueryIsBitLockerVolumeReadOnly@@YAJPEAGPEAE@Z`
- size: `664`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x140122b58`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bc6c`
- `0x140014260`
- `0x14003c69c`
- `0x140088ba4`
- `0x1401228b8`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14012298c`
- `KERNEL32!CreateFileW` at `0x14012298c`
- `KERNEL32!CloseHandle` at `0x140122ab4`
- `KERNEL32!CloseHandle` at `0x140122ab4`
- `KERNEL32!GetLastError` at `0x14012299b`
- `KERNEL32!GetLastError` at `0x1401229a5`
- `KERNEL32!GetLastError` at `0x1401229af`
- `KERNEL32!GetLastError` at `0x140122a4c`
- `KERNEL32!GetLastError` at `0x140122a56`
- `KERNEL32!GetLastError` at `0x140122a60`
- `KERNEL32!GetLastError` at `0x14012299b`
- `KERNEL32!GetLastError` at `0x1401229a5`
- `KERNEL32!GetLastError` at `0x1401229af`
- `KERNEL32!GetLastError` at `0x140122a4c`
- `KERNEL32!GetLastError` at `0x140122a56`
- `KERNEL32!GetLastError` at `0x140122a60`
- `KERNEL32!DeviceIoControl` at `0x140122a42`
- `KERNEL32!DeviceIoControl` at `0x140122a42`
- `ole32!CoTaskMemFree` at `0x140122ace`
- `ole32!CoTaskMemFree` at `0x140122ace`

## string_xrefs

- `0x140122927`: `pbIsReadOnly`

## pseudocode

```c

```

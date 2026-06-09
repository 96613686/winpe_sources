# SetDiskPartionActive(ulong,__int64)

- ea: `0x14007ed60`
- end: `0x14007f353`
- name: `?SetDiskPartionActive@@YAJK_J@Z`
- size: `1523`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task`

## callers

- `0x14007e85c`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000cbcc`
- `0x14001358c`
- `0x140014260`
- `0x14007ed60`
- `0x14007f520`
- `0x14007f578`
- `0x14007f5dc`
- `0x140134d20`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14007ee8e`
- `KERNEL32!CreateFileW` at `0x14007ee8e`
- `KERNEL32!CloseHandle` at `0x14007f2fe`
- `KERNEL32!CloseHandle` at `0x14007f2fe`
- `KERNEL32!GetLastError` at `0x14007eea1`
- `KERNEL32!GetLastError` at `0x14007ef61`
- `KERNEL32!GetLastError` at `0x14007f20f`
- `KERNEL32!GetLastError` at `0x14007eea1`
- `KERNEL32!GetLastError` at `0x14007ef61`
- `KERNEL32!GetLastError` at `0x14007f20f`
- `KERNEL32!DeviceIoControl` at `0x14007ef57`
- `KERNEL32!DeviceIoControl` at `0x14007f205`
- `KERNEL32!DeviceIoControl` at `0x14007ef57`
- `KERNEL32!DeviceIoControl` at `0x14007f205`
- `ole32!CoTaskMemFree` at `0x14007ef09`
- `ole32!CoTaskMemFree` at `0x14007f2f5`
- `ole32!CoTaskMemFree` at `0x14007ef09`
- `ole32!CoTaskMemFree` at `0x14007f2f5`

## string_xrefs

- `0x14007f068`: `base\stor\blb\engine\service\bmr.cpp`

## pseudocode

```c

```

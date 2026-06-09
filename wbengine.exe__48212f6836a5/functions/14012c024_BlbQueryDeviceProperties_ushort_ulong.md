# BlbQueryDeviceProperties(ushort *,ulong *)

- ea: `0x14012c024`
- end: `0x14012c469`
- name: `?BlbQueryDeviceProperties@@YAJPEAGPEAK@Z`
- size: `1093`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x140125bf0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x140014260`
- `0x14012c024`
- `0x14012c470`
- `0x140134d20`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x14012c0db`
- `KERNEL32!CreateFileW` at `0x14012c0db`
- `KERNEL32!CloseHandle` at `0x14012c3bf`
- `KERNEL32!CloseHandle` at `0x14012c3bf`
- `KERNEL32!GetLastError` at `0x14012c0ea`
- `KERNEL32!GetLastError` at `0x14012c196`
- `KERNEL32!GetLastError` at `0x14012c256`
- `KERNEL32!GetLastError` at `0x14012c2ea`
- `KERNEL32!GetLastError` at `0x14012c0ea`
- `KERNEL32!GetLastError` at `0x14012c196`
- `KERNEL32!GetLastError` at `0x14012c256`
- `KERNEL32!GetLastError` at `0x14012c2ea`
- `KERNEL32!DeviceIoControl` at `0x14012c18c`
- `KERNEL32!DeviceIoControl` at `0x14012c24c`
- `KERNEL32!DeviceIoControl` at `0x14012c2e0`
- `KERNEL32!DeviceIoControl` at `0x14012c18c`
- `KERNEL32!DeviceIoControl` at `0x14012c24c`
- `KERNEL32!DeviceIoControl` at `0x14012c2e0`

## string_xrefs

- `0x14012c29b`: `cbRet == sizeof(hotPlugInfo)`

## pseudocode

```c

```

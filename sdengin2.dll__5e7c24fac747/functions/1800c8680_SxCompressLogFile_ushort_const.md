# SxCompressLogFile(ushort const *)

- ea: `0x1800c8680`
- end: `0x1800c87ec`
- name: `?SxCompressLogFile@@YAJPEBG@Z`
- size: `364`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008db40`
- `0x1800952c0`
- `0x1800c8ffc`

## callees

- `0x1800081d8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c8680`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800c8717`
- `KERNEL32!CreateFileW` at `0x1800c8717`
- `KERNEL32!CloseHandle` at `0x1800c87c6`
- `KERNEL32!CloseHandle` at `0x1800c87c6`
- `KERNEL32!DeviceIoControl` at `0x1800c8796`
- `KERNEL32!DeviceIoControl` at `0x1800c8796`

## string_xrefs

- `0x1800c86ce`: `SxCompressLogFile`

## pseudocode

```c

```

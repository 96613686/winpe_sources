# SxCompressLogFile(ushort const *)

- ea: `0x1800ce328`
- end: `0x1800ce4ab`
- name: `?SxCompressLogFile@@YAJPEBG@Z`
- size: `387`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180091a44`
- `0x180099630`
- `0x1800ced14`

## callees

- `0x180008370`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800ce328`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800ce3bf`
- `KERNEL32!CreateFileW` at `0x1800ce3bf`
- `KERNEL32!CloseHandle` at `0x1800ce47e`
- `KERNEL32!CloseHandle` at `0x1800ce47e`
- `KERNEL32!DeviceIoControl` at `0x1800ce448`
- `KERNEL32!DeviceIoControl` at `0x1800ce448`

## string_xrefs

- `0x1800ce376`: `SxCompressLogFile`

## pseudocode

```c

```

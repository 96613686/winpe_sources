# _CheckSMARTFailure(ushort const *,int *)

- ea: `0x180014414`
- end: `0x180014663`
- name: `?_CheckSMARTFailure@@YAJPEBGPEAH@Z`
- size: `591`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800119c4`

## callees

- `0x180014414`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800144f7`
- `KERNEL32!CreateFileW` at `0x1800144f7`
- `KERNEL32!CloseHandle` at `0x180014623`
- `KERNEL32!CloseHandle` at `0x180014623`
- `KERNEL32!DeviceIoControl` at `0x18001456d`
- `KERNEL32!DeviceIoControl` at `0x1800145de`
- `KERNEL32!DeviceIoControl` at `0x18001456d`
- `KERNEL32!DeviceIoControl` at `0x1800145de`

## pseudocode

```c

```

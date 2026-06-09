# _CheckSMARTFailure(ushort const *,int *)

- ea: `0x180013b40`
- end: `0x180013d72`
- name: `?_CheckSMARTFailure@@YAJPEBGPEAH@Z`
- size: `562`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180011274`

## callees

- `0x180013b40`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180013c23`
- `KERNEL32!CreateFileW` at `0x180013c23`
- `KERNEL32!CloseHandle` at `0x180013d39`
- `KERNEL32!CloseHandle` at `0x180013d39`
- `KERNEL32!DeviceIoControl` at `0x180013c93`
- `KERNEL32!DeviceIoControl` at `0x180013cfa`
- `KERNEL32!DeviceIoControl` at `0x180013c93`
- `KERNEL32!DeviceIoControl` at `0x180013cfa`

## pseudocode

```c

```

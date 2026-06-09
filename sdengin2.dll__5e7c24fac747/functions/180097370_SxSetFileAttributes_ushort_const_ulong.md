# SxSetFileAttributes(ushort const *,ulong)

- ea: `0x180097370`
- end: `0x18009759f`
- name: `?SxSetFileAttributes@@YAJPEBGK@Z`
- size: `559`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180096b20`
- `0x180096db0`
- `0x180097cec`

## callees

- `0x1800081d8`
- `0x1800145f4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x18008f660`
- `0x180097370`
- `0x1800c9830`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x180097543`
- `ntdll!NtSetInformationFile` at `0x180097543`
- `ntdll!NtQueryInformationFile` at `0x180097509`
- `ntdll!NtQueryInformationFile` at `0x180097509`
- `KERNEL32!CreateFileW` at `0x180097453`
- `KERNEL32!CreateFileW` at `0x180097453`
- `KERNEL32!CloseHandle` at `0x18009756b`
- `KERNEL32!CloseHandle` at `0x18009756b`

## string_xrefs

- `0x1800973d3`: `SxSetFileAttributes`

## pseudocode

```c

```

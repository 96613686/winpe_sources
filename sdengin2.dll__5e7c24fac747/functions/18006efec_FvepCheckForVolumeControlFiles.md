# FvepCheckForVolumeControlFiles

- ea: `0x18006efec`
- end: `0x18006f26e`
- name: `FvepCheckForVolumeControlFiles`
- size: `642`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18006fa04`

## callees

- `0x18006ed74`
- `0x18006ee08`
- `0x18006ee80`
- `0x18006efec`
- `0x18006fd6c`
- `0x18006fe00`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006f09c`
- `KERNEL32!GetLastError` at `0x18006f237`
- `KERNEL32!GetLastError` at `0x18006f09c`
- `KERNEL32!GetLastError` at `0x18006f237`
- `KERNEL32!CloseHandle` at `0x18006f247`
- `KERNEL32!CloseHandle` at `0x18006f247`
- `KERNEL32!DeviceIoControl` at `0x18006f092`
- `KERNEL32!DeviceIoControl` at `0x18006f092`
- `KERNEL32!GetFileAttributesW` at `0x18006f1f0`
- `KERNEL32!GetFileAttributesW` at `0x18006f20b`
- `KERNEL32!GetFileAttributesW` at `0x18006f1f0`
- `KERNEL32!GetFileAttributesW` at `0x18006f20b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006f22d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006f22d`

## pseudocode

```c

```

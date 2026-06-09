# FvepCheckForVolumeControlFiles

- ea: `0x180071e20`
- end: `0x1800720cd`
- name: `FvepCheckForVolumeControlFiles`
- size: `685`
- prototype: `__int64 __fastcall(HANDLE hDevice)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180072924`

## callees

- `0x180071b54`
- `0x180071bec`
- `0x180071c68`
- `0x180071e20`
- `0x180072cf0`
- `0x180072d84`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180071ed6`
- `KERNEL32!GetLastError` at `0x180072089`
- `KERNEL32!GetLastError` at `0x180071ed6`
- `KERNEL32!GetLastError` at `0x180072089`
- `KERNEL32!CloseHandle` at `0x18007209f`
- `KERNEL32!CloseHandle` at `0x18007209f`
- `KERNEL32!DeviceIoControl` at `0x180071ec6`
- `KERNEL32!DeviceIoControl` at `0x180071ec6`
- `KERNEL32!GetFileAttributesW` at `0x180072030`
- `KERNEL32!GetFileAttributesW` at `0x180072051`
- `KERNEL32!GetFileAttributesW` at `0x180072030`
- `KERNEL32!GetFileAttributesW` at `0x180072051`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180072079`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180072079`

## pseudocode

```c

```

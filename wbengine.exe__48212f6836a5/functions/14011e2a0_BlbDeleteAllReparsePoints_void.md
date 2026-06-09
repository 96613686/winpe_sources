# BlbDeleteAllReparsePoints(void)

- ea: `0x14011e2a0`
- end: `0x14011e5d4`
- name: `?BlbDeleteAllReparsePoints@@YAJXZ`
- size: `820`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, service_task`

## callers

- `0x140043f38`

## callees

- `0x1400063b4`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x140051e98`
- `0x14011e2a0`
- `0x14011eab0`
- `0x140134d20`

## import_xrefs

- `KERNEL32!RemoveDirectoryW` at `0x14011e4f5`
- `KERNEL32!RemoveDirectoryW` at `0x14011e4f5`
- `KERNEL32!FindClose` at `0x14011e3e3`
- `KERNEL32!FindClose` at `0x14011e562`
- `KERNEL32!FindClose` at `0x14011e3e3`
- `KERNEL32!FindClose` at `0x14011e562`
- `KERNEL32!FindNextFileW` at `0x14011e535`
- `KERNEL32!FindNextFileW` at `0x14011e535`
- `KERNEL32!FindFirstFileW` at `0x14011e337`
- `KERNEL32!FindFirstFileW` at `0x14011e435`
- `KERNEL32!FindFirstFileW` at `0x14011e337`
- `KERNEL32!FindFirstFileW` at `0x14011e435`
- `KERNEL32!GetLastError` at `0x14011e347`
- `KERNEL32!GetLastError` at `0x14011e444`
- `KERNEL32!GetLastError` at `0x14011e543`
- `KERNEL32!GetLastError` at `0x14011e347`
- `KERNEL32!GetLastError` at `0x14011e444`
- `KERNEL32!GetLastError` at `0x14011e543`
- `ole32!CoTaskMemFree` at `0x14011e57c`
- `ole32!CoTaskMemFree` at `0x14011e57c`

## string_xrefs

- `0x14011e409`: `WsbMountedVolumeFile*`

## pseudocode

```c

```

# CFileLogger::WriteData(ulong,char * *)

- ea: `0x140114654`
- end: `0x1401148fc`
- name: `?WriteData@CFileLogger@@AEAAJKPEAPEAD@Z`
- size: `680`
- prototype: `int(CFileLogger *__hidden this, unsigned int, char **)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x140114904`
- `0x140114c9c`
- `0x140114cd4`

## callees

- `0x140006ca8`
- `0x140014200`
- `0x140014260`
- `0x140014384`
- `0x14003c434`
- `0x14008863c`
- `0x140114098`
- `0x140114654`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x14011472e`
- `KERNEL32!FormatMessageW` at `0x14011472e`
- `KERNEL32!WriteFile` at `0x140114823`
- `KERNEL32!WriteFile` at `0x140114823`
- `KERNEL32!LocalFree` at `0x1401148db`
- `KERNEL32!LocalFree` at `0x1401148db`
- `KERNEL32!GetLastError` at `0x140114738`
- `KERNEL32!GetLastError` at `0x14011482d`
- `KERNEL32!GetLastError` at `0x140114738`
- `KERNEL32!GetLastError` at `0x14011482d`
- `ole32!CoTaskMemFree` at `0x1401148c8`
- `ole32!CoTaskMemFree` at `0x1401148d1`
- `ole32!CoTaskMemFree` at `0x1401148c8`
- `ole32!CoTaskMemFree` at `0x1401148d1`

## string_xrefs

- `0x140114874`: `dwBytesWritten == dwBytesToWrite`

## pseudocode

```c

```

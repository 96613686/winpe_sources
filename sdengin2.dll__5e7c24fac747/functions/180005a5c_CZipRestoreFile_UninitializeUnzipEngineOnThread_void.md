# CZipRestoreFile::UninitializeUnzipEngineOnThread(void)

- ea: `0x180005a5c`
- end: `0x180005b1e`
- name: `?UninitializeUnzipEngineOnThread@CZipRestoreFile@@SAJXZ`
- size: `194`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002c07c`

## callees

- `0x180005a5c`
- `0x1800081d8`
- `0x18006fe84`
- `0x18006ff8c`
- `0x1800a70e8`

## import_xrefs

- `KERNEL32!GlobalHandle` at `0x180005aa7`
- `KERNEL32!GlobalHandle` at `0x180005aa7`
- `KERNEL32!GlobalUnlock` at `0x180005ab8`
- `KERNEL32!GlobalUnlock` at `0x180005ab8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005a8e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005a8e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005acf`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005acf`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005ac1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005ac1`

## string_xrefs

- `0x180005a6e`: `CZipRestoreFile::UninitializeUnzipEngineOnThread`

## pseudocode

```c

```

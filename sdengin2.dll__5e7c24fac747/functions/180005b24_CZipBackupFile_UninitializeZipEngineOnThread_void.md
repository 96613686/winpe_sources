# CZipBackupFile::UninitializeZipEngineOnThread(void)

- ea: `0x180005b24`
- end: `0x180005bd3`
- name: `?UninitializeZipEngineOnThread@CZipBackupFile@@SAJXZ`
- size: `175`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001fd38`

## callees

- `0x180005b24`
- `0x1800081d8`
- `0x18006fe84`
- `0x18006ff8c`

## import_xrefs

- `KERNEL32!GlobalHandle` at `0x180005b64`
- `KERNEL32!GlobalHandle` at `0x180005b64`
- `KERNEL32!GlobalUnlock` at `0x180005b70`
- `KERNEL32!GlobalUnlock` at `0x180005b70`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005b56`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005b56`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005b87`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005b87`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005b79`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005b79`

## string_xrefs

- `0x180005b36`: `CZipBackupFile::UninitializeZipEngineOnThread`

## pseudocode

```c

```

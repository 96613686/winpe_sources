# CZipBackupFile::UninitializeZipEngineOnThread(void)

- ea: `0x180005c04`
- end: `0x180005cd2`
- name: `?UninitializeZipEngineOnThread@CZipBackupFile@@SAJXZ`
- size: `206`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800208dc`

## callees

- `0x180005c04`
- `0x180008370`
- `0x180072e08`
- `0x180072f14`

## import_xrefs

- `KERNEL32!GlobalHandle` at `0x180005c4a`
- `KERNEL32!GlobalHandle` at `0x180005c4a`
- `KERNEL32!GlobalUnlock` at `0x180005c5c`
- `KERNEL32!GlobalUnlock` at `0x180005c5c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005c36`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180005c36`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005c7f`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180005c7f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005c6b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005c6b`

## string_xrefs

- `0x180005c16`: `CZipBackupFile::UninitializeZipEngineOnThread`

## pseudocode

```c

```

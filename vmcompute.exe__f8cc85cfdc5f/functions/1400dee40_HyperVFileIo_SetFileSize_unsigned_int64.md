# HyperVFileIo::SetFileSize(unsigned __int64)

- ea: `0x1400dee40`
- end: `0x1400def51`
- name: `?SetFileSize@HyperVFileIo@@UEAAX_K@Z`
- size: `273`
- prototype: `void(HyperVFileIo *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400def60`

## callees

- `0x1400c40e0`
- `0x1400dee40`
- `0x1400e07f8`
- `0x1400e0900`
- `0x140279680`
- `0x140279eac`
- `0x14027a048`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400dee9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400deeff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400dee9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400deeff`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1400deeeb`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1400deeeb`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1400dee87`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1400dee87`

## string_xrefs

- `0x1400dee62`: `onecore\vm\common\hypervstorage\hypervfileio.cpp`

## pseudocode

```c

```

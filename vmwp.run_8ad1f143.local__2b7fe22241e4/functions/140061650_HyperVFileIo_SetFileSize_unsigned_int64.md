# HyperVFileIo::SetFileSize(unsigned __int64)

- ea: `0x140061650`
- end: `0x140061761`
- name: `?SetFileSize@HyperVFileIo@@UEAAX_K@Z`
- size: `273`
- prototype: `void(HyperVFileIo *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400612d0`

## callees

- `0x140028218`
- `0x140061650`
- `0x14006af58`
- `0x1400db620`
- `0x1401cbd90`
- `0x1401cc918`
- `0x1401ccab4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400616ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006170f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400616ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006170f`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1400616fb`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1400616fb`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x140061697`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x140061697`

## string_xrefs

- `0x140061672`: `onecore\vm\common\hypervstorage\hypervfileio.cpp`

## pseudocode

```c

```

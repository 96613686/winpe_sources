# HyperVFileIo::SetFileSize(unsigned __int64)

- ea: `0x14006f390`
- end: `0x14006f4a1`
- name: `?SetFileSize@HyperVFileIo@@UEAAX_K@Z`
- size: `273`
- prototype: `void(HyperVFileIo *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14006f010`

## callees

- `0x140028788`
- `0x14006f390`
- `0x140078628`
- `0x1400cba80`
- `0x1401bb260`
- `0x1401bbde8`
- `0x1401bbf84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006f3eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006f44f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006f3eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006f44f`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x14006f43b`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x14006f43b`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x14006f3d7`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x14006f3d7`

## string_xrefs

- `0x14006f3b2`: `onecore\vm\common\hypervstorage\hypervfileio.cpp`

## pseudocode

```c

```

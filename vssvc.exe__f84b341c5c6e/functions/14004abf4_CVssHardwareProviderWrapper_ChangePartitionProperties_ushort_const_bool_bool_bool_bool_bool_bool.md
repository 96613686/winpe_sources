# CVssHardwareProviderWrapper::ChangePartitionProperties(ushort const *,bool,bool,bool,bool,bool,bool *)

- ea: `0x14004abf4`
- end: `0x14004b0c5`
- name: `?ChangePartitionProperties@CVssHardwareProviderWrapper@@AEAAXPEBG_N1111PEA_N@Z`
- size: `1233`
- prototype: `void(CVssHardwareProviderWrapper *__hidden this, const unsigned __int16 *, bool, bool, bool, bool, bool, bool *)`
- caller_count: `6`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14004ba1c`
- `0x140053174`
- `0x1400b2350`
- `0x1400bd7a8`
- `0x1400bf9fc`
- `0x1400c03ec`

## callees

- `0x1400137c0`
- `0x140013b00`
- `0x14003c174`
- `0x14003fcac`
- `0x140049ec4`
- `0x14004abf4`
- `0x140091560`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ace1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004adb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004af0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004ace1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004adb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004af0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004b010`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14004acbf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14004acbf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14004ada9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14004af03`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14004afc0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14004b006`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14004ada9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14004af03`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14004afc0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x14004b006`

## string_xrefs

- `0x14004ad4d`: `CreateFile(Volume %s)`
- `0x14004af6d`: `DeviceIoControl(FSCTL_DISMOUNT_VOLUME)`

## pseudocode

```c

```

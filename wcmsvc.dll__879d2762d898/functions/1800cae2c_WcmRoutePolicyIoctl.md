# WcmRoutePolicyIoctl

- ea: `0x1800cae2c`
- end: `0x1800cb001`
- name: `WcmRoutePolicyIoctl`
- size: `469`
- prototype: `__int64 __fastcall(DWORD dwIoControlCode, LPVOID lpInBuffer, DWORD nInBufferSize)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x1800caca0`
- `0x1800cacf0`
- `0x1800cadcc`

## callees

- `0x1800091f4`
- `0x18001c254`
- `0x18003a08c`
- `0x180061ddc`
- `0x1800622cc`
- `0x18006283c`
- `0x180084f50`
- `0x1800cae2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800caf67`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800caf67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800caf0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800caf0f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800cae62`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800cae62`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800caf01`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800caf01`

## string_xrefs

- `0x1800cae74`: `onecoreuap\net\wcm\service\base\selection\lib\routepolicydriver.cpp`
- `0x1800caf3a`: `onecoreuap\net\wcm\service\base\selection\lib\routepolicydriver.cpp`
- `0x1800caf82`: `onecoreuap\net\wcm\service\base\selection\lib\routepolicydriver.cpp`
- `0x1800cafb5`: `onecoreuap\net\wcm\service\base\selection\lib\routepolicydriver.cpp`

## pseudocode

```c

```

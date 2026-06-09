# CAgentDownloadManager::OnUpdateDownloadProgress(DownloadManagerUpdateID const &,int)

- ea: `0x18008a914`
- end: `0x18008b45f`
- name: `?OnUpdateDownloadProgress@CAgentDownloadManager@@AEAAXAEBUDownloadManagerUpdateID@@H@Z`
- size: `2891`
- prototype: `void __fastcall(CAgentDownloadManager *__hidden this, const struct DownloadManagerUpdateID *, int)`
- caller_count: `3`
- callee_count: `34`
- tags: `service_task, installer_update`

## callers

- `0x1800817a0`
- `0x1800a1254`
- `0x1800a3034`

## callees

- `0x18000def4`
- `0x18003b230`
- `0x18003baf4`
- `0x18007e2d4`
- `0x180088cbc`
- `0x180089da8`
- `0x18008a194`
- `0x18008a644`
- `0x18008a914`
- `0x18008f66c`
- `0x180095b60`
- `0x1800aa93c`
- `0x1800aaefc`
- `0x1800aafc4`
- `0x1800ab8b0`
- `0x1800ad298`
- `0x1800ae39c`
- `0x1800aec5c`
- `0x1800cc95c`
- `0x1800cca78`
- `0x1800ccb10`
- `0x1800ccccc`
- `0x1800e8b58`
- `0x1800e9ebc`
- `0x1800ea0b4`
- `0x1800eab98`
- `0x1800eac24`
- `0x1800eac74`
- `0x18010eef8`
- `0x180113ae8`
- `0x18012b618`
- `0x18012bf80`
- `0x180238960`
- `0x18023afb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008aa2c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008aa2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008b3e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008b3e1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008aadb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008ac08`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008aadb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18008ac08`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18008aa0f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18008b349`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18008aa0f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18008b349`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008ac4c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008ac4c`

## string_xrefs

- `0x18008abb7`: `C:\__w\1\s\src\Client\Engine\Agent\downloadmanager.cpp`
- `0x18008acff`: `C:\__w\1\s\src\Client\Engine\Agent\downloadmanager.cpp`
- `0x18008ad7a`: `C:\__w\1\s\src\Client\Engine\Agent\downloadmanager.cpp`
- `0x18008a976`: `Progress made on update %ws; notifying dependent calls if significant.`
- `0x18008acaa`: `ByteRangeFindTotalDownloadSizeEnd UpdateId: %ws. IsInteractive: %ws, CallerId: %ws.`
- `0x18008ad10`: `Failed to get first non-framework update title`
- `0x18008adbc`: `Not able to extract productId from update title %ws`
- `0x18008b3b5`: `OnUpdateDownloadProgress: update %ws, relevant jobs=%u, duration=%lu`
- `0x18008ab23`: `C:\__w\1\s\src\Client\Engine\Agent\DownloadCall.cpp`

## pseudocode

```c

```

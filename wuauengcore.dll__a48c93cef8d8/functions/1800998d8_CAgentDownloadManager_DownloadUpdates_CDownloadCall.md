# CAgentDownloadManager::DownloadUpdates(CDownloadCall *)

- ea: `0x1800998d8`
- end: `0x18009a13c`
- name: `?DownloadUpdates@CAgentDownloadManager@@QEAAXPEAVCDownloadCall@@@Z`
- size: `2148`
- prototype: `void __fastcall(CAgentDownloadManager *__hidden this, struct CDownloadCall *)`
- caller_count: `1`
- callee_count: `37`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800cbe40`

## callees

- `0x180036560`
- `0x18003baf4`
- `0x1800582c8`
- `0x18005c9a4`
- `0x180060988`
- `0x18007e2d4`
- `0x18007ef74`
- `0x180083ca4`
- `0x180086640`
- `0x180090338`
- `0x180092354`
- `0x180094a50`
- `0x180094fd0`
- `0x180095e8c`
- `0x180099094`
- `0x1800998d8`
- `0x1800a65cc`
- `0x1800a8f90`
- `0x1800a91fc`
- `0x1800ae39c`
- `0x1800aec5c`
- `0x1800b20ec`
- `0x1800b2e9c`
- `0x1800b34b0`
- `0x1800b67b0`
- `0x1800c887c`
- `0x1800cd8fc`
- `0x1800cea68`
- `0x1800cee7c`
- `0x1800eacd8`
- `0x1800eb154`
- `0x1800eb5dc`
- `0x18012b618`
- `0x18012bed4`
- `0x180238984`
- `0x180239110`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180099da1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180099da1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180099dc7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180099dc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099e65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099fff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099e65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180099fff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a04d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009a04d`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180099f90`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180099f90`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180099fba`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180099fba`

## string_xrefs

- `0x180099ad1`: `* START * Begin Downloading Updates [CallerId = %ws] [Call ID = %ws]`
- `0x180099c0c`: `Priority = %d, NetworkCostPolicy = %d, Interactive = %ws, Download on Battery = %ws, Bypass Regulation = %ws, Owner is system = %ws, Proxy session id = %lu, Download Type = %d, ServiceId = %ws, IsSerialized = %ws.`
- `0x180099c22`: `Updates to download = %lu`
- `0x180099d4f`: `Not refreshing regulator because service is shutting down.`
- `0x18009a0c9`: `* END * Begin Downloading Updates [CallerId = %ws] [Call ID = %ws] [hr = 0x%08X]`
- `0x180099a4c`: `C:\__w\1\s\src\Client\Engine\Agent\UpdateApprovalList.cpp`

## pseudocode

```c

```

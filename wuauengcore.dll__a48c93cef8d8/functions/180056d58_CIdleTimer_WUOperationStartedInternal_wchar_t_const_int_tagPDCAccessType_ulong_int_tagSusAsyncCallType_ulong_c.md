# CIdleTimer::WUOperationStartedInternal(wchar_t const *,int,tagPDCAccessType,ulong *,int,tagSusAsyncCallType,ulong,char const *,bool)

- ea: `0x180056d58`
- end: `0x1800574fa`
- name: `?WUOperationStartedInternal@CIdleTimer@@QEAAJPEB_WHW4tagPDCAccessType@@PEAKHW4tagSusAsyncCallType@@KPEBD_N@Z`
- size: `1954`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x180056cc0`

## callees

- `0x18000def4`
- `0x180036560`
- `0x180055ce4`
- `0x1800566a4`
- `0x180056d58`
- `0x180057ac8`
- `0x180057f98`
- `0x1800582c8`
- `0x180058518`
- `0x18005fad8`
- `0x18010eec4`
- `0x180110d24`
- `0x180113ae8`
- `0x18012b618`
- `0x180238960`
- `0x180239110`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056f19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056f64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057426`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800574c8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056f19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180056f64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180057426`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800574c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056f28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056f3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800572b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005745d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800574d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056f28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180056f3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800572b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005745d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800574d1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180057316`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180057316`

## string_xrefs

- `0x1800573a0`: `C:\__w\1\s\src\Client\Engine\Agent\IdleTimer.cpp`
- `0x1800574ab`: `C:\__w\1\s\src\Client\Engine\Agent\IdleTimer.cpp`
- `0x180056dcb`: `Attempted to start WU operation when idle timer wasn't initialized`
- `0x180056f82`: `Next task operation handle is 0 (NoOperation); skipping to 1`

## pseudocode

```c

```

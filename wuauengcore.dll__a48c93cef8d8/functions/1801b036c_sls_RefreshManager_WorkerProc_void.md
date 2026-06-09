# sls::RefreshManager::WorkerProc(void)

- ea: `0x1801b036c`
- end: `0x1801b0558`
- name: `?WorkerProc@RefreshManager@sls@@AEAAKXZ`
- size: `492`
- prototype: `unsigned int __fastcall(sls::RefreshManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1801b0360`

## callees

- `0x18012b618`
- `0x1801b036c`
- `0x1801b0560`
- `0x1801b08f0`
- `0x1801b09d4`
- `0x180238960`
- `0x180238984`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801b03fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801b03fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b040a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b043d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b040a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801b043d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b0538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b0538`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801b050e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801b050e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801b03ba`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1801b03ba`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1801b04ae`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1801b04ae`

## string_xrefs

- `0x1801b04bc`: `Refresh worker thread shutting down`
- `0x1801b0466`: `Worker complete`
- `0x1801b0392`: `RefreshMgr Worker Thread started`
- `0x1801b04f1`: `RefreshMgr Worker Thread STOP`

## pseudocode

```c

```

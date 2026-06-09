# CHangrepServer::StaticActivationQuiesceReportCompletedCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x1800254e0`
- end: `0x18002555f`
- name: `?StaticActivationQuiesceReportCompletedCallback@CHangrepServer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `127`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180013df4`
- `0x1800254e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002550e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002550e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025541`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025541`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x18002554d`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x18002554d`

## pseudocode

```c

```

# kfapi::CFolderCache::GetIDList(_GUID const &,void *,ulong,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x180036040`
- end: `0x180036d36`
- name: `?GetIDList@CFolderCache@kfapi@@QEAAJAEBU_GUID@@PEAXKPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `3318`
- prototype: `int(kfapi::CFolderCache *__hidden this, const struct _GUID *, void *, unsigned int, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180035f40`

## callees

- `0x180033c60`
- `0x1800344f0`
- `0x180034e90`
- `0x1800351e0`
- `0x1800356f0`
- `0x180036040`
- `0x180039f10`
- `0x180074ca4`
- `0x180076040`
- `0x1800763f8`
- `0x180077ea0`
- `0x1800ff94c`
- `0x1801d92ec`
- `0x1801d935c`
- `0x1801d9400`
- `0x1801d942c`
- `0x1801d973c`
- `0x18022bc44`
- `0x1802537d0`
- `0x180266be4`
- `0x1803b1f60`
- `0x1803b243c`
- `0x1803b2ac0`
- `0x1803b66ac`
- `0x1803b6714`
- `0x1803b69b9`
- `0x1803b69c5`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036142`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800364e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800369d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036c91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036142`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800364e2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800369d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036c91`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003640c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036602`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036a93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036cea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003640c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036602`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036a93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036cea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003686d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003686d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003664e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003664e`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180036672`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180036672`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800367d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036c5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036cf9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800367d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036c5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036cf9`
- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x18003694f`
- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x18003694f`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180036153`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800364f1`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18003650f`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180036153`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x1800364f1`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18003650f`

## pseudocode

```c

```

# kfapi::CFolderCache::GetIDList(_GUID const &,void *,ulong,_ITEMIDLIST_ABSOLUTE * *)

- ea: `0x180040570`
- end: `0x1800411e8`
- name: `?GetIDList@CFolderCache@kfapi@@QEAAJAEBU_GUID@@PEAXKPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `3192`
- prototype: `int(kfapi::CFolderCache *__hidden this, const struct _GUID *, void *, unsigned int, struct _ITEMIDLIST_ABSOLUTE **)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180040480`

## callees

- `0x18000ee84`
- `0x180019a5c`
- `0x18001a76c`
- `0x18003eb30`
- `0x18003ed40`
- `0x18003f430`
- `0x18003f780`
- `0x18003fc84`
- `0x180040570`
- `0x180044240`
- `0x1800a444c`
- `0x1801ccd50`
- `0x1801ccdc0`
- `0x1802126b4`
- `0x180218608`
- `0x180218908`
- `0x180242804`
- `0x180257fe4`
- `0x18025f68c`
- `0x180282dcc`
- `0x1803a4cb0`
- `0x1803a518c`
- `0x1803a57e0`
- `0x1803a93cc`
- `0x1803a9434`
- `0x1803a96d9`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040672`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800409fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040eb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041158`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040672`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800409fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040eb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041158`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004092c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040b04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040f6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800411ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004092c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040b04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040f6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800411ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180040d56`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180040d56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040b4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180040b4a`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180040b68`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x180040b68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040cc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004112b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800411b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180040cc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004112b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800411b4`
- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x180040e32`
- `SHCORE!__imp_SHRegGetBoolValueFromHKCUHKLM` at `0x180040e32`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18004067d`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180040a05`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180040a1d`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x18004067d`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180040a05`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180040a1d`

## pseudocode

```c

```

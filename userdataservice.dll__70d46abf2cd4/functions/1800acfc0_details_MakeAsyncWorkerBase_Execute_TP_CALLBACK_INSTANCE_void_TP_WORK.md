# details::MakeAsyncWorkerBase::Execute(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x1800acfc0`
- end: `0x1800ad0ad`
- name: `?Execute@MakeAsyncWorkerBase@details@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `237`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008f0c`
- `0x180075f98`
- `0x1800acfc0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad02d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad02d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800ad003`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800ad003`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x1800ad072`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x1800ad072`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800ad05d`
- `api-ms-win-core-com-l1-1-0!CoDecrementMTAUsage` at `0x1800ad05d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800ad023`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800ad023`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800ad097`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800ad097`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800acfda`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800acfda`

## pseudocode

```c

```

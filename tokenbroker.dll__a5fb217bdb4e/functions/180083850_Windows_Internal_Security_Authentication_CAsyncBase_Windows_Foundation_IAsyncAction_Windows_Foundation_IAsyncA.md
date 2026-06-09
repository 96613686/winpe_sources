# Windows::Internal::Security::Authentication::CAsyncBase<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::Security::Authentication::Web::PushCookiesParams,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const Windows::Internal::Security::Authentication::Web::PushCookiesAsyncActionName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::WorkerStub(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180083850`
- end: `0x1800839bb`
- name: `?WorkerStub@?$CAsyncBase@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@UPushCookiesParams@Web@Authentication@Security@Internal@3@U?$AsyncCausalityOptions@$1?PushCookiesAsyncActionName@Web@Authentication@Security@Internal@Windows@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Authentication@Security@Internal@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `363`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180083850`
- `0x1800839c4`
- `0x18011b010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008395d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008395d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800838b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800838b1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800838c4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800838c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800838ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800838ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083967`
- `api-ms-win-core-threadpool-l1-2-0!FreeLibraryWhenCallbackReturns` at `0x1800839b4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180083997`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180083997`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180083891`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180083891`

## pseudocode

```c

```

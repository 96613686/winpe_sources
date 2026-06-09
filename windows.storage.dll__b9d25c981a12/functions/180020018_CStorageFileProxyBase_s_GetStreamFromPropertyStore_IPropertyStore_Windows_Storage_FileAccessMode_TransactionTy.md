# CStorageFileProxyBase::s_GetStreamFromPropertyStore(IPropertyStore *,Windows::Storage::FileAccessMode,TransactionType,Windows::Storage::StorageOpenOptions,Windows::System::IUser *,_GUID const &,void * *)

- ea: `0x180020018`
- end: `0x180020347`
- name: `?s_GetStreamFromPropertyStore@CStorageFileProxyBase@@KAJPEAUIPropertyStore@@W4FileAccessMode@Storage@Windows@@W4TransactionType@@W4StorageOpenOptions@45@PEAUIUser@System@5@AEBU_GUID@@PEAPEAX@Z`
- size: `815`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180020458`
- `0x180023a38`
- `0x1800283c8`
- `0x1801fdb88`

## callees

- `0x180009fc0`
- `0x1800118c4`
- `0x180020018`
- `0x180020350`
- `0x180033c60`
- `0x180038f50`
- `0x18007ea3c`
- `0x18007ea60`
- `0x1800801ac`
- `0x180083c94`
- `0x1803b1f60`
- `0x1803bd8c4`
- `0x1803d2c48`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18065f6ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18065f6c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18065f6ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18065f6c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800202ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800202ae`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18065f6f2`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18065f6f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020324`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002022b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020240`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002022b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020240`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800200ec`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800200ec`
- `SHCORE!__imp_CreateRandomAccessStreamOnFileWithOptions` at `0x1800201c1`
- `SHCORE!__imp_CreateRandomAccessStreamOnFileWithOptions` at `0x1800201c1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800202f2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800202f2`

## pseudocode

```c

```

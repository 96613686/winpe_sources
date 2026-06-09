# CDynamicDownloadDataFetcher::AddUpdateToFetch(SusWsStructs::SusUpdateIdentity,_GUID *,ulong,CCallerIdentity const *)

- ea: `0x1800ec988`
- end: `0x1800ecc09`
- name: `?AddUpdateToFetch@CDynamicDownloadDataFetcher@@QEAAJUSusUpdateIdentity@SusWsStructs@@PEAU_GUID@@KPEBVCCallerIdentity@@@Z`
- size: `641`
- prototype: `int __high(struct SusWsStructs::SusUpdateIdentity, struct _GUID *, unsigned int, const struct CCallerIdentity *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800a4c84`

## callees

- `0x1800ec988`
- `0x1800ef684`
- `0x1800ef9a0`
- `0x180105194`
- `0x180105908`
- `0x180113ae8`
- `0x18012b618`
- `0x180238960`
- `0x180238984`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eca6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eca6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ecba1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ecbdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ecba1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ecbdc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800eca11`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800eca21`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800eca11`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800eca21`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ecad4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ecb4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ecad4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800ecb4d`

## string_xrefs

- `0x1800ecb38`: `DynamicDownloadDataFetcher: %ws - added new entry for Update %ws.%u`
- `0x1800eca4d`: `DynamicDownloadDataFetcher: %ws - Update %ws,%u is being added to fetcher.`
- `0x1800ecb53`: `DynamicDownloadDataFetcher: %ws - updated existing entry for Update %ws.%u`

## pseudocode

```c

```

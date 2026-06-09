# CClientCallRecorder::SetDownloadProperties(_GUID const &,wchar_t const *,tagDownloadPriority,tagNetworkCostPolicy,int,unsigned __int64,tagProxySettings const *,ulong)

- ea: `0x180048460`
- end: `0x1800488ee`
- name: `?SetDownloadProperties@CClientCallRecorder@@UEAAJAEBU_GUID@@PEB_WW4tagDownloadPriority@@W4tagNetworkCostPolicy@@H_KPEBUtagProxySettings@@K@Z`
- size: `1166`
- prototype: `__int64 __fastcall(__int64, struct _GUID *, const WCHAR *, int, int, int, void *, __int64, int)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000def4`
- `0x180031354`
- `0x18003d95c`
- `0x18003efbc`
- `0x180048460`
- `0x180048c18`
- `0x1800ca5b8`
- `0x1801051cc`
- `0x180106dec`
- `0x180110914`
- `0x180113ae8`
- `0x18012b618`
- `0x18012bed4`
- `0x180238960`
- `0x180238984`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800485c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048763`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800485c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048763`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004878c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048839`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004889a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004878c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048839`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004889a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004872e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18004872e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180048582`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180048582`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18004859c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18004859c`

## string_xrefs

- `0x180048605`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x1800487b3`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x180048875`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`

## pseudocode

```c

```

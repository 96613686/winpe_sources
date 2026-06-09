# WwanSapGetNotification(WWAN_SAP *,_RPC_ASYNC_STATE *,_L2_NOTIFICATION_DATA * *)

- ea: `0x1800b2158`
- end: `0x1800b222b`
- name: `?WwanSapGetNotification@@YAKPEAUWWAN_SAP@@PEAU_RPC_ASYNC_STATE@@PEAPEAU_L2_NOTIFICATION_DATA@@@Z`
- size: `211`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, PRPC_ASYNC_STATE pAsync, struct _L2_NOTIFICATION_DATA **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800ac430`

## callees

- `0x180012300`
- `0x1800b2158`
- `0x1800b6384`
- `0x1800b63d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2178`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800b2178`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2188`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b21a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b21eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2205`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2188`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b21a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b21eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b2205`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800b2213`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800b2213`

## string_xrefs

- `0x1800b21a7`: `wwan completing async call with error`

## pseudocode

```c

```

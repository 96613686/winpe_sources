# Wwan2SapGetNotification(WWAN_SAP *,_RPC_ASYNC_STATE *,_L2_NOTIFICATION_DATA * *)

- ea: `0x1800af714`
- end: `0x1800af7e7`
- name: `?Wwan2SapGetNotification@@YAKPEAUWWAN_SAP@@PEAU_RPC_ASYNC_STATE@@PEAPEAU_L2_NOTIFICATION_DATA@@@Z`
- size: `211`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, PRPC_ASYNC_STATE pAsync, struct _L2_NOTIFICATION_DATA **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800abd90`

## callees

- `0x180012300`
- `0x1800af714`
- `0x1800b6384`
- `0x1800b63d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800af734`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800af734`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af744`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af75d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af7a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af7c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af744`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af75d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af7a7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800af7c1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800af7cf`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800af7cf`

## string_xrefs

- `0x1800af763`: `wwan2 completing rpc async call with error`

## pseudocode

```c

```

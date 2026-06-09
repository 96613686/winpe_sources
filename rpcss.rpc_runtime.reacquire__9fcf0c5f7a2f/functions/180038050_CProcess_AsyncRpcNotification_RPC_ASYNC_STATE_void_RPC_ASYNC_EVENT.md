# CProcess::AsyncRpcNotification(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)

- ea: `0x180038050`
- end: `0x18003821f`
- name: `?AsyncRpcNotification@CProcess@@CAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z`
- size: `463`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *, void *, enum _RPC_ASYNC_EVENT)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180038050`
- `0x1800387b8`
- `0x18008172c`
- `0x1800b7e90`
- `0x180114010`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180038072`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180038072`
- `RPCRT4!RpcBindingFree` at `0x1800380ce`
- `RPCRT4!RpcBindingFree` at `0x1800380ce`
- `RPCRT4!RpcBindingSetOption` at `0x1800380ac`
- `RPCRT4!RpcBindingSetOption` at `0x1800380ac`
- `RPCRT4!RpcBindingUnbind` at `0x1800380bd`
- `RPCRT4!RpcBindingUnbind` at `0x1800380bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038164`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038181`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038164`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038181`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003810c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003810c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038147`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038147`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003819b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003819b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800381be`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800381be`

## string_xrefs

- `0x18003820e`: `onecore\com\combase\rpcss\objex\process.cxx`

## pseudocode

```c

```

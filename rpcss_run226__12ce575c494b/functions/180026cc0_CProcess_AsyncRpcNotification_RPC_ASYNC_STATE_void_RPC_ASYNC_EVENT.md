# CProcess::AsyncRpcNotification(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)

- ea: `0x180026cc0`
- end: `0x180026e52`
- name: `?AsyncRpcNotification@CProcess@@CAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z`
- size: `402`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *, void *, enum _RPC_ASYNC_EVENT)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180026cc0`
- `0x1800273c4`
- `0x18007e3d4`
- `0x1800b2bb0`
- `0x18010b010`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180026ce2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180026ce2`
- `RPCRT4!RpcBindingFree` at `0x180026d2c`
- `RPCRT4!RpcBindingFree` at `0x180026d2c`
- `RPCRT4!RpcBindingSetOption` at `0x180026d16`
- `RPCRT4!RpcBindingSetOption` at `0x180026d16`
- `RPCRT4!RpcBindingUnbind` at `0x180026d21`
- `RPCRT4!RpcBindingUnbind` at `0x180026d21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026db0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026dc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026db0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180026dc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026d64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026d64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026d99`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026d99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026ddb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026ddb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026df8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026df8`

## string_xrefs

- `0x180026e41`: `onecore\com\combase\rpcss\objex\process.cxx`

## pseudocode

```c

```

# AsyncRPCEventClient::saveAsyncParams(_RPC_ASYNC_STATE *,_WIA_ASYNC_EVENT_NOTIFY_DATA *)

- ea: `0x180053788`
- end: `0x180053b29`
- name: `?saveAsyncParams@AsyncRPCEventClient@@QEAAJPEAU_RPC_ASYNC_STATE@@PEAU_WIA_ASYNC_EVENT_NOTIFY_DATA@@@Z`
- size: `929`
- prototype: `__int64 __fastcall(AsyncRPCEventClient *__hidden this, struct _RPC_ASYNC_STATE *, struct _WIA_ASYNC_EVENT_NOTIFY_DATA *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x180053130`

## callees

- `0x18000ac34`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18001e014`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180053788`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180053b08`
- `KERNEL32!LeaveCriticalSection` at `0x180053b08`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800538fb`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800538fb`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x180053a1e`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x180053a1e`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18005384c`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18005384c`

## string_xrefs

- `0x18005392a`: `We caught exception 0x%08X trying to update client's async state`
- `0x180053958`: `We caught exception 0x%08X trying to update client's async state`

## pseudocode

```c

```

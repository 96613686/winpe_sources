# RpcServer::SecurityCallback(void *,void *)

- ea: `0x180046f70`
- end: `0x180047067`
- name: `?SecurityCallback@RpcServer@@CAJPEAX0@Z`
- size: `247`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180025de4`
- `0x180042200`
- `0x180046f70`
- `0x1800829fa`
- `0x180082a40`

## import_xrefs

- `RPCRT4!UuidEqual` at `0x180046fec`
- `RPCRT4!UuidEqual` at `0x180046fec`
- `RPCRT4!RpcRevertToSelf` at `0x180047037`
- `RPCRT4!RpcRevertToSelf` at `0x180047037`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180046fae`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180046fae`

## string_xrefs

- `0x18004700b`: `RpcServer::SecurityCallback`

## pseudocode

```c

```

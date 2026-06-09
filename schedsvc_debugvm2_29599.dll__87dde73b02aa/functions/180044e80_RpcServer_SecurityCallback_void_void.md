# RpcServer::SecurityCallback(void *,void *)

- ea: `0x180044e80`
- end: `0x180044f60`
- name: `?SecurityCallback@RpcServer@@CAJPEAX0@Z`
- size: `224`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18002f35c`
- `0x180040590`
- `0x180044e80`
- `0x18007e68a`
- `0x18007e6d0`

## import_xrefs

- `RPCRT4!UuidEqual` at `0x180044ef2`
- `RPCRT4!UuidEqual` at `0x180044ef2`
- `RPCRT4!RpcRevertToSelf` at `0x180044f37`
- `RPCRT4!RpcRevertToSelf` at `0x180044f37`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180044ebe`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180044ebe`

## string_xrefs

- `0x180044f0b`: `RpcServer::SecurityCallback`

## pseudocode

```c

```

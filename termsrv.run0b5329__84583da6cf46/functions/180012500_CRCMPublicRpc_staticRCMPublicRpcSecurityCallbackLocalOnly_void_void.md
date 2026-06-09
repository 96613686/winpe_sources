# CRCMPublicRpc::staticRCMPublicRpcSecurityCallbackLocalOnly(void *,void *)

- ea: `0x180012500`
- end: `0x1800126bc`
- name: `?staticRCMPublicRpcSecurityCallbackLocalOnly@CRCMPublicRpc@@CAJPEAX0@Z`
- size: `444`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000a210`
- `0x180012500`
- `0x1800321f0`
- `0x1800330c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800125b3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800125c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800125b3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800125c6`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001263b`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18001263b`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18001254e`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18001254e`
- `RPCRT4!RpcStringFreeW` at `0x180012682`
- `RPCRT4!RpcStringFreeW` at `0x180012693`
- `RPCRT4!RpcStringFreeW` at `0x180012682`
- `RPCRT4!RpcStringFreeW` at `0x180012693`
- `RPCRT4!RpcStringBindingParseW` at `0x180012595`
- `RPCRT4!RpcStringBindingParseW` at `0x180012595`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800125f8`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800125f8`

## string_xrefs

- `0x180012614`: `Client is using named pipe and we allow local access only`

## pseudocode

```c

```

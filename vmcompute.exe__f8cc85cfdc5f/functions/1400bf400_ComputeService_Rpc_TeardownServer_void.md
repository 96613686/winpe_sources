# ComputeService::Rpc::TeardownServer(void)

- ea: `0x1400bf400`
- end: `0x1400bf4ca`
- name: `?TeardownServer@Rpc@ComputeService@@YAXXZ`
- size: `202`
- prototype: `void __fastcall(ComputeService::Rpc *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14011dd44`

## callees

- `0x1400beb00`
- `0x1400bf400`
- `0x1400bf4d0`
- `0x1401332f0`

## import_xrefs

- `RPCRT4!RpcServerInqBindings` at `0x1400bf421`
- `RPCRT4!RpcServerInqBindings` at `0x1400bf421`
- `RPCRT4!RpcEpUnregister` at `0x1400bf440`
- `RPCRT4!RpcEpUnregister` at `0x1400bf440`
- `RPCRT4!RpcServerUnregisterIf` at `0x1400bf459`
- `RPCRT4!RpcServerUnregisterIf` at `0x1400bf459`
- `WS2_32!__imp_WSAGetLastError` at `0x1400bf475`
- `WS2_32!__imp_WSAGetLastError` at `0x1400bf475`
- `WS2_32!__imp_WSACleanup` at `0x1400bf465`
- `WS2_32!__imp_WSACleanup` at `0x1400bf465`

## string_xrefs

- `0x1400bf499`: `onecore\vm\compute\rpc\server\rpcserver.cpp`

## pseudocode

```c

```

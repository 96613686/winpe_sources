# RpcServer::StopTask(ushort const *,ulong)

- ea: `0x180076dcc`
- end: `0x180077083`
- name: `?StopTask@RpcServer@@QEAAJPEBGK@Z`
- size: `695`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, unsigned __int16 *p_psz, int)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800779d0`

## callees

- `0x180001008`
- `0x18000b4e0`
- `0x18001a430`
- `0x180022600`
- `0x1800230c0`
- `0x180023b60`
- `0x180025310`
- `0x18002f35c`
- `0x18002f3e0`
- `0x180039d00`
- `0x180039d30`
- `0x180040590`
- `0x180040900`
- `0x180040b70`
- `0x18004ac58`
- `0x180076dcc`
- `0x1800772d0`
- `0x18007e68a`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180076f8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180076f8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180076fcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180076fd3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180076fcb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180076fd3`
- `RPCRT4!RpcRevertToSelf` at `0x180076eb3`
- `RPCRT4!RpcRevertToSelf` at `0x180076f35`
- `RPCRT4!RpcRevertToSelf` at `0x180076f49`
- `RPCRT4!RpcRevertToSelf` at `0x180076eb3`
- `RPCRT4!RpcRevertToSelf` at `0x180076f35`
- `RPCRT4!RpcRevertToSelf` at `0x180076f49`

## string_xrefs

- `0x180076e80`: `RpcServer::StopTask`
- `0x180076f0a`: `RpcServer::StopTask`
- `0x180076ec7`: `StopTask`

## pseudocode

```c

```

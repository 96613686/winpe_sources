# RpcServer::SetTaskDisabledForCurrentUser(ushort const *,uchar)

- ea: `0x1800769dc`
- end: `0x180076c1a`
- name: `?SetTaskDisabledForCurrentUser@RpcServer@@QEAAJPEBGE@Z`
- size: `574`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, unsigned __int16 *, char)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task`

## callers

- `0x180077820`

## callees

- `0x18000b4e0`
- `0x18001a430`
- `0x180022600`
- `0x1800230c0`
- `0x180023b60`
- `0x180025310`
- `0x18002f3e0`
- `0x180039d00`
- `0x180039d30`
- `0x180040590`
- `0x180040900`
- `0x180056794`
- `0x1800769dc`
- `0x18007e68a`
- `0x18007e6d0`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180076b3e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180076b3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180076b63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180076bc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180076b63`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180076bc5`
- `RPCRT4!RpcRevertToSelf` at `0x180076ace`
- `RPCRT4!RpcRevertToSelf` at `0x180076aed`
- `RPCRT4!RpcRevertToSelf` at `0x180076ace`
- `RPCRT4!RpcRevertToSelf` at `0x180076aed`

## string_xrefs

- `0x180076b01`: `SetTaskDisabledForCurrentUser`
- `0x180076a62`: `RpcServer::SetTaskDisabledForCurrentUser`

## pseudocode

```c

```

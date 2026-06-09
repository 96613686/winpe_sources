# RpcServer::SetTaskDisabledForCurrentUser(ushort const *,uchar)

- ea: `0x18007a9dc`
- end: `0x18007ac39`
- name: `?SetTaskDisabledForCurrentUser@RpcServer@@QEAAJPEBGE@Z`
- size: `605`
- prototype: `int(RpcServer *__hidden this, const unsigned __int16 *, unsigned __int8)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task`

## callers

- `0x18007b900`

## callees

- `0x18000fe50`
- `0x180013a90`
- `0x1800141e0`
- `0x18001ea40`
- `0x18001f060`
- `0x180020110`
- `0x180024590`
- `0x180024730`
- `0x180025e70`
- `0x180041610`
- `0x180042200`
- `0x180059140`
- `0x18007a9dc`
- `0x1800829fa`
- `0x180082a40`
- `0x180088010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007ab4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18007ab4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007ab75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007abdd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007ab75`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18007abdd`
- `RPCRT4!RpcRevertToSelf` at `0x18007aace`
- `RPCRT4!RpcRevertToSelf` at `0x18007aaf3`
- `RPCRT4!RpcRevertToSelf` at `0x18007aace`
- `RPCRT4!RpcRevertToSelf` at `0x18007aaf3`

## string_xrefs

- `0x18007aa62`: `RpcServer::SetTaskDisabledForCurrentUser`
- `0x18007ab0d`: `SetTaskDisabledForCurrentUser`

## pseudocode

```c

```

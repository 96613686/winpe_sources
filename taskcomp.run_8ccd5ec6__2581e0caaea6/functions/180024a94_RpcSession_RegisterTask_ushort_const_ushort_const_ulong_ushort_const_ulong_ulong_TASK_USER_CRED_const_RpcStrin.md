# RpcSession::RegisterTask(ushort const *,ushort const *,ulong,ushort const *,ulong,ulong,_TASK_USER_CRED const *,RpcString &,RpcXmlErrorInfo &)

- ea: `0x180024a94`
- end: `0x180024b6a`
- name: `?RegisterTask@RpcSession@@QEBAJPEBG0K0KKPEBU_TASK_USER_CRED@@AEAVRpcString@@AEAVRpcXmlErrorInfo@@@Z`
- size: `214`
- prototype: `__int64 __fastcall(RpcSession *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, unsigned int, const struct _TASK_USER_CRED *, struct RpcString *, struct RpcXmlErrorInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000b218`

## callees

- `0x180024a94`
- `0x180024ca4`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180024b2f`
- `RPCRT4!NdrClientCall3` at `0x180024b2f`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032016`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032016`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024ab9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024ab9`

## pseudocode

```c

```

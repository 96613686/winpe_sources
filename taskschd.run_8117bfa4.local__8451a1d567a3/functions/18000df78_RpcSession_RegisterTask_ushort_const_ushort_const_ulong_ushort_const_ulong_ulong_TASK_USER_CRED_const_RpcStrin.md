# RpcSession::RegisterTask(ushort const *,ushort const *,ulong,ushort const *,ulong,ulong,_TASK_USER_CRED const *,RpcString &,RpcXmlErrorInfo &)

- ea: `0x18000df78`
- end: `0x18000e065`
- name: `?RegisterTask@RpcSession@@QEBAJPEBG0K0KKPEBU_TASK_USER_CRED@@AEAVRpcString@@AEAVRpcXmlErrorInfo@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(RpcSession *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, unsigned int, const struct _TASK_USER_CRED *, struct RpcString *, struct RpcXmlErrorInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000f69c`

## callees

- `0x18000cd10`
- `0x18000df78`
- `0x180039fbc`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e01e`
- `RPCRT4!NdrClientCall3` at `0x18000e01e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180053ad6`
- `RPCRT4!I_RpcExceptionFilter` at `0x180053ad6`

## pseudocode

```c

```

# RpcSession::RegisterTask(ushort const *,ushort const *,ulong,ushort const *,ulong,ulong,_TASK_USER_CRED const *,RpcString &,RpcXmlErrorInfo &)

- ea: `0x18000d8ac`
- end: `0x18000d992`
- name: `?RegisterTask@RpcSession@@QEBAJPEBG0K0KKPEBU_TASK_USER_CRED@@AEAVRpcString@@AEAVRpcXmlErrorInfo@@@Z`
- size: `230`
- prototype: `CLIENT_CALL_RETURN __fastcall(RpcSession *this, const unsigned __int16 *, const unsigned __int16 *, int, const unsigned __int16 *, unsigned int, unsigned int, const struct _TASK_USER_CRED *, struct RpcString *, struct RpcXmlErrorInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000f374`

## callees

- `0x18000c750`
- `0x18000d8ac`
- `0x180037124`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000d952`
- `RPCRT4!NdrClientCall3` at `0x18000d952`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fdda`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fdda`

## pseudocode

```c

```

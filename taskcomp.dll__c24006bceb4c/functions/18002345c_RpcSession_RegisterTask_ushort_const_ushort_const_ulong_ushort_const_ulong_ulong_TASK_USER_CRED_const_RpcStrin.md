# RpcSession::RegisterTask(ushort const *,ushort const *,ulong,ushort const *,ulong,ulong,_TASK_USER_CRED const *,RpcString &,RpcXmlErrorInfo &)

- ea: `0x18002345c`
- end: `0x180023525`
- name: `?RegisterTask@RpcSession@@QEBAJPEBG0K0KKPEBU_TASK_USER_CRED@@AEAVRpcString@@AEAVRpcXmlErrorInfo@@@Z`
- size: `201`
- prototype: `__int64 __fastcall(RpcSession *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, unsigned int, const struct _TASK_USER_CRED *, struct RpcString *, struct RpcXmlErrorInfo *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000ac28`

## callees

- `0x18002345c`
- `0x180023648`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800234f1`
- `RPCRT4!NdrClientCall3` at `0x1800234f1`
- `RPCRT4!I_RpcExceptionFilter` at `0x18002fecc`
- `RPCRT4!I_RpcExceptionFilter` at `0x18002fecc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023481`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023481`

## pseudocode

```c

```

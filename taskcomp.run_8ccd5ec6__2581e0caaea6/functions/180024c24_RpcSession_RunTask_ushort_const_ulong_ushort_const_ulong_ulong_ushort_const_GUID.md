# RpcSession::RunTask(ushort const *,ulong,ushort const * *,ulong,ulong,ushort const *,_GUID *)

- ea: `0x180024c24`
- end: `0x180024c9c`
- name: `?RunTask@RpcSession@@QEBAJPEBGKPEAPEBGKK0PEAU_GUID@@@Z`
- size: `120`
- prototype: `__int64 __fastcall(RpcSession *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 **, unsigned int, unsigned int, const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180012f5c`

## callees

- `0x180024c24`
- `0x180024ca4`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180024c69`
- `RPCRT4!NdrClientCall3` at `0x180024c69`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032066`
- `RPCRT4!I_RpcExceptionFilter` at `0x180032066`

## pseudocode

```c

```

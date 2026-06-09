# RpcSession::RetrieveTask(ushort const *,ushort const *,ulong *,RpcString &)

- ea: `0x18001fa40`
- end: `0x18001fae6`
- name: `?RetrieveTask@RpcSession@@QEBAJPEBG0PEAKAEAVRpcString@@@Z`
- size: `166`
- prototype: `__int64 __fastcall(RpcSession *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, struct RpcString *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180005e20`
- `0x18001e890`
- `0x18001fda0`

## callees

- `0x18001fa40`
- `0x180037124`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fa77`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001fa77`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fa69`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001fa69`
- `RPCRT4!NdrClientCall3` at `0x18001fab1`
- `RPCRT4!NdrClientCall3` at `0x18001fab1`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050bae`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050bae`

## pseudocode

```c

```

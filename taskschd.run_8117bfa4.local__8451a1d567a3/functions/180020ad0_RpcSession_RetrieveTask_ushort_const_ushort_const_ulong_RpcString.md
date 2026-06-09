# RpcSession::RetrieveTask(ushort const *,ushort const *,ulong *,RpcString &)

- ea: `0x180020ad0`
- end: `0x180020b89`
- name: `?RetrieveTask@RpcSession@@QEBAJPEBG0PEAKAEAVRpcString@@@Z`
- size: `185`
- prototype: `__int64 __fastcall(RpcSession *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, struct RpcString *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800060d0`
- `0x18001f8c0`
- `0x180020e40`

## callees

- `0x180020ad0`
- `0x180039fbc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020b0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020b0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020af9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020af9`
- `RPCRT4!NdrClientCall3` at `0x180020b4d`
- `RPCRT4!NdrClientCall3` at `0x180020b4d`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800548ee`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800548ee`

## pseudocode

```c

```

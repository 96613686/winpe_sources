# CProcess::UpdateResolverBindings(unsigned __int64,tagDUALSTRINGARRAY const *)

- ea: `0x1800654f8`
- end: `0x1800657e2`
- name: `?UpdateResolverBindings@CProcess@@QEAAJ_KPEBUtagDUALSTRINGARRAY@@@Z`
- size: `746`
- prototype: `__int64 __fastcall(CProcess *__hidden this, unsigned __int64, const struct tagDUALSTRINGARRAY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x180034910`

## callees

- `0x18002c2f0`
- `0x180034260`
- `0x180058880`
- `0x1800654f8`
- `0x18006ff00`
- `0x1800b7e90`
- `0x1800b8428`
- `0x1800c20bc`
- `0x180114010`

## import_xrefs

- `RPCRT4!NdrAsyncClientCall` at `0x1800656e6`
- `RPCRT4!NdrAsyncClientCall` at `0x1800656e6`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800655f6`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x1800655f6`
- `RPCRT4!RpcBindingFree` at `0x180065651`
- `RPCRT4!RpcBindingFree` at `0x180065651`
- `RPCRT4!RpcBindingSetOption` at `0x180065629`
- `RPCRT4!RpcBindingSetOption` at `0x180065629`
- `RPCRT4!RpcBindingUnbind` at `0x18006563d`
- `RPCRT4!RpcBindingUnbind` at `0x18006563d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800655a8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800655a8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180065526`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180065526`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065558`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006558b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180065558`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006558b`

## string_xrefs

- `0x1800656f9`: `UpdateResolverBindings this:%p PID:%x %ws %!WINERROR!`
- `0x180065719`: `CProcess::UpdateResolverBindings`
- `0x180065781`: `CProcess::UpdateResolverBindings`

## pseudocode

```c

```

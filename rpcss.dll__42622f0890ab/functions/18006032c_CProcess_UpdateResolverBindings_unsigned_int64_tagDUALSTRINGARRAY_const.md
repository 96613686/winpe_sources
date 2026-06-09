# CProcess::UpdateResolverBindings(unsigned __int64,tagDUALSTRINGARRAY const *)

- ea: `0x18006032c`
- end: `0x1800605df`
- name: `?UpdateResolverBindings@CProcess@@QEAAJ_KPEBUtagDUALSTRINGARRAY@@@Z`
- size: `691`
- prototype: `__int64 __fastcall(CProcess *__hidden this, unsigned __int64, const struct tagDUALSTRINGARRAY *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1800453a4`

## callees

- `0x180034540`
- `0x1800531a0`
- `0x18006032c`
- `0x1800652c0`
- `0x18006afb0`
- `0x1800b2bb0`
- `0x1800b3128`
- `0x1800bc780`
- `0x18010b010`

## import_xrefs

- `RPCRT4!NdrAsyncClientCall` at `0x1800604e9`
- `RPCRT4!NdrAsyncClientCall` at `0x1800604e9`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180060411`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180060411`
- `RPCRT4!RpcBindingFree` at `0x18006045a`
- `RPCRT4!RpcBindingFree` at `0x18006045a`
- `RPCRT4!RpcBindingSetOption` at `0x18006043e`
- `RPCRT4!RpcBindingSetOption` at `0x18006043e`
- `RPCRT4!RpcBindingUnbind` at `0x18006044c`
- `RPCRT4!RpcBindingUnbind` at `0x18006044c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800603c9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800603c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006035a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006035a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060386`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800603b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060386`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800603b2`

## string_xrefs

- `0x1800604f6`: `UpdateResolverBindings this:%p PID:%x %ws %!WINERROR!`
- `0x180060516`: `CProcess::UpdateResolverBindings`
- `0x18006057e`: `CProcess::UpdateResolverBindings`

## pseudocode

```c

```

# ControlServiceExW

- ea: `0x180015850`
- end: `0x180015975`
- name: `ControlServiceExW`
- size: `293`
- prototype: `BOOL __stdcall(SC_HANDLE hService, DWORD dwControl, DWORD dwInfoLevel, PVOID pControlParams)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180015850`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015961`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015961`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015955`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015955`
- `RPCRT4!NdrClientCall2` at `0x180015900`
- `RPCRT4!NdrClientCall2` at `0x180015900`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050180`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050180`

## pseudocode

```c

```

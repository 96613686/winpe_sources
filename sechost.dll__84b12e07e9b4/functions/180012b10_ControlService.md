# ControlService

- ea: `0x180012b10`
- end: `0x180012b6c`
- name: `ControlService`
- size: `92`
- prototype: `BOOL __stdcall(SC_HANDLE hService, DWORD dwControl, LPSERVICE_STATUS lpServiceStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180012b10`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012b58`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012b58`
- `RPCRT4!NdrClientCall2` at `0x180012b36`
- `RPCRT4!NdrClientCall2` at `0x180012b36`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004ffde`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004ffde`

## pseudocode

```c

```

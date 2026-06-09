# QueryServiceStatus

- ea: `0x180013670`
- end: `0x1800136c7`
- name: `QueryServiceStatus`
- size: `87`
- prototype: `BOOL __stdcall(SC_HANDLE hService, LPSERVICE_STATUS lpServiceStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180013670`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800136b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800136b3`
- `RPCRT4!NdrClientCall2` at `0x180013691`
- `RPCRT4!NdrClientCall2` at `0x180013691`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005009e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005009e`

## pseudocode

```c

```

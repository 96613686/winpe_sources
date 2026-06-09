# GetServiceKeyNameW

- ea: `0x180016c40`
- end: `0x180016cdd`
- name: `GetServiceKeyNameW`
- size: `157`
- prototype: `BOOL __stdcall(SC_HANDLE hSCManager, LPCWSTR lpDisplayName, LPWSTR lpServiceName, LPDWORD lpcchBuffer)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180016c40`
- `0x180016d94`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016c6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016c6a`
- `RPCRT4!NdrClientCall2` at `0x180016cac`
- `RPCRT4!NdrClientCall2` at `0x180016cac`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800502ac`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800502ac`

## pseudocode

```c

```

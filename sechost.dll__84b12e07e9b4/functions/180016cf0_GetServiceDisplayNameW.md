# GetServiceDisplayNameW

- ea: `0x180016cf0`
- end: `0x180016d8d`
- name: `GetServiceDisplayNameW`
- size: `157`
- prototype: `BOOL __stdcall(SC_HANDLE hSCManager, LPCWSTR lpServiceName, LPWSTR lpDisplayName, LPDWORD lpcchBuffer)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180016cf0`
- `0x180016d94`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016d1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016d1a`
- `RPCRT4!NdrClientCall2` at `0x180016d5c`
- `RPCRT4!NdrClientCall2` at `0x180016d5c`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800502ce`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800502ce`

## pseudocode

```c

```

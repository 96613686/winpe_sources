# QueryServiceConfigW

- ea: `0x18000f310`
- end: `0x18000f466`
- name: `QueryServiceConfigW`
- size: `342`
- prototype: `BOOL __stdcall(SC_HANDLE hService, LPQUERY_SERVICE_CONFIGW lpServiceConfig, DWORD cbBufSize, LPDWORD pcbBytesNeeded)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x18000f310`
- `0x180013630`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f40b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f40b`
- `RPCRT4!NdrClientCall2` at `0x18000f387`
- `RPCRT4!NdrClientCall2` at `0x18000f387`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fece`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004feea`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fece`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004feea`

## pseudocode

```c

```

# QueryServiceStatusEx

- ea: `0x180012b80`
- end: `0x180012c27`
- name: `QueryServiceStatusEx`
- size: `167`
- prototype: `BOOL __stdcall(SC_HANDLE hService, SC_STATUS_TYPE InfoLevel, LPBYTE lpBuffer, DWORD cbBufSize, LPDWORD pcbBytesNeeded)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18003bfa0`

## callees

- `0x180012b80`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012bf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012c11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012c1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012bf1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012c11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012c1d`
- `RPCRT4!NdrClientCall2` at `0x180012bc2`
- `RPCRT4!NdrClientCall2` at `0x180012bc2`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005000e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005000e`

## pseudocode

```c

```

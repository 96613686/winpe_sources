# EnumDependentServicesW

- ea: `0x180039380`
- end: `0x180039523`
- name: `EnumDependentServicesW`
- size: `419`
- prototype: `BOOL __stdcall(SC_HANDLE hService, DWORD dwServiceState, LPENUM_SERVICE_STATUSW lpServices, DWORD cbBufSize, LPDWORD pcbBytesNeeded, LPDWORD lpServicesReturned)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000e9a0`
- `0x180039380`
- `0x18004abac`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800394f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800394f4`
- `RPCRT4!NdrClientCall2` at `0x180039432`
- `RPCRT4!NdrClientCall2` at `0x180039432`

## pseudocode

```c

```

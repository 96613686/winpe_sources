# EnumServicesStatusExW

- ea: `0x18000e220`
- end: `0x18000e4cc`
- name: `EnumServicesStatusExW`
- size: `684`
- prototype: `BOOL __stdcall(SC_HANDLE hSCManager, SC_ENUM_TYPE InfoLevel, DWORD dwServiceType, DWORD dwServiceState, LPBYTE lpServices, DWORD cbBufSize, LPDWORD pcbBytesNeeded, LPDWORD lpServicesReturned, LPDWORD lpResumeHandle, LPCWSTR pszGroupName)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000e220`
- `0x18000e9a0`
- `0x18004abac`
- `0x18004fa50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e3f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e4a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e3f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e4a3`
- `RPCRT4!NdrClientCall2` at `0x18000e350`
- `RPCRT4!NdrClientCall2` at `0x18000e350`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fdee`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fdee`

## pseudocode

```c

```

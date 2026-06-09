# QueryServiceConfigA

- ea: `0x18003a060`
- end: `0x18003a166`
- name: `QueryServiceConfigA`
- size: `262`
- prototype: `BOOL __stdcall(SC_HANDLE hService, LPQUERY_SERVICE_CONFIGA lpServiceConfig, DWORD cbBufSize, LPDWORD pcbBytesNeeded)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x18003a060`
- `0x18003c930`
- `0x18004abac`
- `0x18004f91a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a12a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a12a`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050620`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005063c`
- `RPCRT4!I_RpcExceptionFilter` at `0x180050620`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005063c`

## pseudocode

```c

```

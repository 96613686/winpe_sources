# StartServiceW

- ea: `0x180015a40`
- end: `0x180015a9c`
- name: `StartServiceW`
- size: `92`
- prototype: `BOOL __stdcall(SC_HANDLE hService, DWORD dwNumServiceArgs, LPCWSTR *lpServiceArgVectors)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180015a40`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015a88`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015a88`
- `RPCRT4!NdrClientCall2` at `0x180015a66`
- `RPCRT4!NdrClientCall2` at `0x180015a66`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800501c4`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800501c4`

## pseudocode

```c

```

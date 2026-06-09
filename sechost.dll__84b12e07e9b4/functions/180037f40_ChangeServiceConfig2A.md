# ChangeServiceConfig2A

- ea: `0x180037f40`
- end: `0x1800380c8`
- name: `ChangeServiceConfig2A`
- size: `392`
- prototype: `BOOL __stdcall(SC_HANDLE hService, DWORD dwInfoLevel, LPVOID lpInfo)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x1800198d8`
- `0x180037f40`
- `0x18004a88c`
- `0x18004a8c0`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800380a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800380a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037fb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037fb3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037f9d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037f9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038000`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038099`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038000`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038099`
- `RPCRT4!NdrClientCall2` at `0x18003805c`
- `RPCRT4!NdrClientCall2` at `0x18003805c`

## pseudocode

```c

```

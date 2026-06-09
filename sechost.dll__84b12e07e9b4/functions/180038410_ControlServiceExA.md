# ControlServiceExA

- ea: `0x180038410`
- end: `0x180038542`
- name: `ControlServiceExA`
- size: `306`
- prototype: `BOOL __stdcall(SC_HANDLE hService, DWORD dwControl, DWORD dwInfoLevel, PVOID pControlParams)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180038410`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038526`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038526`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003851a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003851a`
- `RPCRT4!NdrClientCall2` at `0x1800384c8`
- `RPCRT4!NdrClientCall2` at `0x1800384c8`

## pseudocode

```c

```

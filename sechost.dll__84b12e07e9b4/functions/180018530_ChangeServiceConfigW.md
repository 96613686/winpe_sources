# ChangeServiceConfigW

- ea: `0x180018530`
- end: `0x180018695`
- name: `ChangeServiceConfigW`
- size: `357`
- prototype: `BOOL __stdcall(SC_HANDLE hService, DWORD dwServiceType, DWORD dwStartType, DWORD dwErrorControl, LPCWSTR lpBinaryPathName, LPCWSTR lpLoadOrderGroup, LPDWORD lpdwTagId, LPCWSTR lpDependencies, LPCWSTR lpServiceStartName, LPCWSTR lpPassword, LPCWSTR lpDisplayName)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x180018530`
- `0x18004a934`
- `0x18004aa18`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018585`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018677`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018585`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018677`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001866b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001866b`
- `RPCRT4!NdrClientCall2` at `0x180018634`
- `RPCRT4!NdrClientCall2` at `0x180018634`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800503bf`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800503bf`

## pseudocode

```c

```

# RpcWinStationGetAllProcesses_NT6

- ea: `0x180061880`
- end: `0x180061d47`
- name: `RpcWinStationGetAllProcesses_NT6`
- size: `1223`
- prototype: `char __fastcall(__int64, int *, int, unsigned int *, struct _TS_ALL_PROCESSES_INFO_NT6 **)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation`

## callers

- `0x180061870`

## callees

- `0x180008b40`
- `0x18000a210`
- `0x18000bad0`
- `0x18000f080`
- `0x18000f1a0`
- `0x1800130d8`
- `0x180013150`
- `0x1800148d0`
- `0x1800241f0`
- `0x1800321f0`
- `0x180060548`
- `0x1800609e8`
- `0x180061880`
- `0x1800b986c`
- `0x1800b9978`
- `0x1800b9d84`
- `0x1800b9e30`
- `0x1800c8010`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180061cd3`
- `RPCRT4!RpcRevertToSelf` at `0x180061cd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061bb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061c0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061c1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061caa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061bb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061c0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061c1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061caa`

## string_xrefs

- `0x1800619da`: `CRpcUtils::GetClientToken failed: 0x%x in %s`

## pseudocode

```c

```

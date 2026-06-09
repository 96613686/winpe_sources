# RpcWinStationShutdownSystem

- ea: `0x18002e920`
- end: `0x18002ed2b`
- name: `RpcWinStationShutdownSystem`
- size: `1035`
- prototype: `char __fastcall(__int64, int *, int, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation`

## callees

- `0x180008b40`
- `0x18000a210`
- `0x18000bad0`
- `0x18000c2f0`
- `0x18000f080`
- `0x18000f1a0`
- `0x180012480`
- `0x180013150`
- `0x1800148d0`
- `0x1800241f0`
- `0x18002e920`
- `0x1800321f0`
- `0x180060548`
- `0x1800b8124`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002ec93`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18002ec93`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002ecb0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002ecb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ecf8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ecf8`
- `RPCRT4!RpcRevertToSelf` at `0x18002e9af`
- `RPCRT4!RpcRevertToSelf` at `0x18002e9af`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18002ecdc`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18002ecdc`

## string_xrefs

- `0x18002ea61`: `CRpcUtils::GetClientToken failed: 0x%x in %s`

## pseudocode

```c

```

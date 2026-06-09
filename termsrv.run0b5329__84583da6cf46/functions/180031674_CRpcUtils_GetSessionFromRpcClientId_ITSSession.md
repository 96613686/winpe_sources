# CRpcUtils::GetSessionFromRpcClientId(ITSSession * *)

- ea: `0x180031674`
- end: `0x180031786`
- name: `?GetSessionFromRpcClientId@CRpcUtils@@SAJPEAPEAUITSSession@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(struct ITSSession **)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18002d5d0`
- `0x180030d80`
- `0x180030f30`
- `0x1800310f0`
- `0x1800312b0`
- `0x180031490`
- `0x18005b120`
- `0x18005f310`

## callees

- `0x18000a210`
- `0x1800130d8`
- `0x180013150`
- `0x180031674`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800316df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800316df`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800316d5`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800316d5`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800316a6`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1800316a6`

## pseudocode

```c

```

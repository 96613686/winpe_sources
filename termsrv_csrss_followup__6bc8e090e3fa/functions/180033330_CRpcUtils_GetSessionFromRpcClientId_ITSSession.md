# CRpcUtils::GetSessionFromRpcClientId(ITSSession * *)

- ea: `0x180033330`
- end: `0x180033455`
- name: `?GetSessionFromRpcClientId@CRpcUtils@@SAJPEAPEAUITSSession@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(struct ITSSession **)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18002efd0`
- `0x180032a00`
- `0x180032bc0`
- `0x180032d90`
- `0x180032f60`
- `0x180033140`
- `0x18005de80`
- `0x180062310`

## callees

- `0x180009940`
- `0x180013948`
- `0x1800139c0`
- `0x180033330`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800333a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800333a7`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180033397`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180033397`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180033362`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180033362`

## pseudocode

```c

```

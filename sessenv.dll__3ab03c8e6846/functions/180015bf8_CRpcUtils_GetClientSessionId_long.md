# CRpcUtils::GetClientSessionId(long *)

- ea: `0x180015bf8`
- end: `0x180015ca5`
- name: `?GetClientSessionId@CRpcUtils@@SAJPEAJ@Z`
- size: `173`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800270e0`

## callees

- `0x180003f30`
- `0x180015bf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015c6a`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180015c60`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180015c60`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180015c21`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180015c21`

## pseudocode

```c

```

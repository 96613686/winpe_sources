# CImpersonate::StopImpersonating(void)

- ea: `0x180018394`
- end: `0x1800183f0`
- name: `?StopImpersonating@CImpersonate@@QEAAJXZ`
- size: `92`
- prototype: `__int64 __fastcall(CImpersonate *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029fe8`
- `0x18002aa3c`
- `0x1800500a0`
- `0x18005289c`
- `0x180053cb0`
- `0x180055d8c`
- `0x18006e1f4`
- `0x18008c970`

## callees

- `0x180018394`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800183d4`
- `RPCRT4!RpcRevertToSelf` at `0x1800183a8`
- `RPCRT4!RpcRevertToSelf` at `0x1800183a8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800183c4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800183c4`

## pseudocode

```c

```

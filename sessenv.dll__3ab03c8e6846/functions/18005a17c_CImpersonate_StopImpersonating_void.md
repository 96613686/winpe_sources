# CImpersonate::StopImpersonating(void)

- ea: `0x18005a17c`
- end: `0x18005a1c5`
- name: `?StopImpersonating@CImpersonate@@QEAAJXZ`
- size: `73`
- prototype: `__int64 __fastcall(CImpersonate *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013160`
- `0x180026fd0`
- `0x1800270e0`

## callees

- `0x18005a17c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a1b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a1b0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005a1a6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005a1a6`
- `RPCRT4!RpcRevertToSelf` at `0x18005a190`
- `RPCRT4!RpcRevertToSelf` at `0x18005a190`

## pseudocode

```c

```

# CImpersonate::StopImpersonating(void)

- ea: `0x180017758`
- end: `0x1800177a1`
- name: `?StopImpersonating@CImpersonate@@QEAAJXZ`
- size: `73`
- prototype: `__int64 __fastcall(CImpersonate *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028a4c`
- `0x18002943c`
- `0x18004da60`
- `0x1800501dc`
- `0x1800515a0`
- `0x180053628`
- `0x18006aee8`
- `0x180088e90`

## callees

- `0x180017758`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001778c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001778c`
- `RPCRT4!RpcRevertToSelf` at `0x18001776c`
- `RPCRT4!RpcRevertToSelf` at `0x18001776c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017782`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180017782`

## pseudocode

```c

```

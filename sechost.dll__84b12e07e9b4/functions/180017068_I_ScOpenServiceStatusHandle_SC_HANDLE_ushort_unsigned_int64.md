# I_ScOpenServiceStatusHandle(SC_HANDLE__ *,ushort *,unsigned __int64)

- ea: `0x180017068`
- end: `0x1800170dd`
- name: `?I_ScOpenServiceStatusHandle@@YAPEAUSC_HANDLE__@@PEAU1@PEAG_K@Z`
- size: `117`
- prototype: `struct SC_HANDLE__ *__fastcall(struct SC_HANDLE__ *, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000bfb0`

## callees

- `0x180017068`
- `0x18004abac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800170c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800170c9`
- `RPCRT4!NdrClientCall2` at `0x1800170a7`
- `RPCRT4!NdrClientCall2` at `0x1800170a7`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800502f0`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800502f0`

## pseudocode

```c

```

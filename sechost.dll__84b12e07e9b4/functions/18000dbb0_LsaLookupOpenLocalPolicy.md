# LsaLookupOpenLocalPolicy

- ea: `0x18000dbb0`
- end: `0x18000dc32`
- name: `LsaLookupOpenLocalPolicy`
- size: `130`
- prototype: `NTSTATUS __stdcall(PLSA_OBJECT_ATTRIBUTES ObjectAttributes, ACCESS_MASK AccessMask, PLSA_LOOKUP_HANDLE PolicyHandle)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000cbf8`
- `0x18000ce20`
- `0x18000d710`
- `0x1800204c8`
- `0x1800231e8`

## callees

- `0x18000dbb0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000dbf2`
- `RPCRT4!NdrClientCall3` at `0x18000dbf2`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fd4e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18004fd4e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000dc05`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000dc05`

## pseudocode

```c

```

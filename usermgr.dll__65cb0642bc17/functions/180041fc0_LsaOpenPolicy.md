# LsaOpenPolicy

- ea: `0x180041fc0`
- end: `0x18004216a`
- name: `LsaOpenPolicy`
- size: `426`
- prototype: `NTSTATUS __stdcall(PLSA_UNICODE_STRING SystemName, PLSA_OBJECT_ATTRIBUTES ObjectAttributes, ACCESS_MASK DesiredAccess, PLSA_HANDLE PolicyHandle)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004cf48`
- `0x18004ea38`
- `0x1800a0128`
- `0x1800dd888`

## callees

- `0x180041fc0`
- `0x1800daa60`
- `0x1800daac4`
- `0x1800dad74`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18004209f`
- `RPCRT4!I_RpcMapWin32Status` at `0x18004211e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18004209f`
- `RPCRT4!I_RpcMapWin32Status` at `0x18004211e`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800e14c9`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800e14e5`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800e14c9`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800e14e5`
- `RPCRT4!NdrClientCall3` at `0x180042105`
- `RPCRT4!NdrClientCall3` at `0x180042105`

## pseudocode

```c

```

# LsaOpenPolicy

- ea: `0x180014d30`
- end: `0x180014fc6`
- name: `LsaOpenPolicy`
- size: `662`
- prototype: `NTSTATUS __stdcall(PLSA_UNICODE_STRING SystemName, PLSA_OBJECT_ATTRIBUTES ObjectAttributes, ACCESS_MASK DesiredAccess, PLSA_HANDLE PolicyHandle)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180014d30`
- `0x1800151ac`
- `0x180016810`
- `0x18003d2a8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014db3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180014db3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014e20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014e20`
- `RPCRT4!NdrClientCall3` at `0x180014ebe`
- `RPCRT4!NdrClientCall3` at `0x180014f52`
- `RPCRT4!NdrClientCall3` at `0x180014ebe`
- `RPCRT4!NdrClientCall3` at `0x180014f52`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800500fe`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005011a`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800500fe`
- `RPCRT4!I_RpcExceptionFilter` at `0x18005011a`
- `RPCRT4!I_RpcMapWin32Status` at `0x180014eec`
- `RPCRT4!I_RpcMapWin32Status` at `0x180014f6a`
- `RPCRT4!I_RpcMapWin32Status` at `0x180014eec`
- `RPCRT4!I_RpcMapWin32Status` at `0x180014f6a`

## pseudocode

```c

```

# LsaCreateSecret

- ea: `0x18003d330`
- end: `0x18003d48e`
- name: `LsaCreateSecret`
- size: `350`
- prototype: `NTSTATUS __stdcall(LSA_HANDLE PolicyHandle, PLSA_UNICODE_STRING SecretName, ACCESS_MASK DesiredAccess, PLSA_HANDLE SecretHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800151ac`
- `0x18003d330`
- `0x18003e360`
- `0x18003e514`
- `0x18004c304`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18003d3f4`
- `RPCRT4!NdrClientCall3` at `0x18003d417`
- `RPCRT4!NdrClientCall3` at `0x18003d3f4`
- `RPCRT4!NdrClientCall3` at `0x18003d417`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003d42c`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003d42c`

## pseudocode

```c

```

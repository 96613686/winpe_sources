# LsaAddAccountRights

- ea: `0x18003c970`
- end: `0x18003c9e8`
- name: `LsaAddAccountRights`
- size: `120`
- prototype: `NTSTATUS __stdcall(LSA_HANDLE PolicyHandle, PSID AccountSid, PLSA_UNICODE_STRING UserRights, ULONG CountOfRights)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18003c970`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18003c9ba`
- `RPCRT4!NdrClientCall3` at `0x18003c9ba`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003c9cd`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003c9cd`

## pseudocode

```c

```

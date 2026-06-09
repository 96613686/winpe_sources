# LsaRemoveAccountRights

- ea: `0x18003cb60`
- end: `0x18003cbe6`
- name: `LsaRemoveAccountRights`
- size: `134`
- prototype: `NTSTATUS __stdcall(LSA_HANDLE PolicyHandle, PSID AccountSid, BOOLEAN AllRights, PLSA_UNICODE_STRING UserRights, ULONG CountOfRights)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18003cb60`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18003cbb8`
- `RPCRT4!NdrClientCall3` at `0x18003cbb8`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003cbcb`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003cbcb`

## pseudocode

```c

```

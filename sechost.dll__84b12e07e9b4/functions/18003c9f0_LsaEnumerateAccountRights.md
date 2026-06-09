# LsaEnumerateAccountRights

- ea: `0x18003c9f0`
- end: `0x18003caa1`
- name: `LsaEnumerateAccountRights`
- size: `177`
- prototype: `NTSTATUS __stdcall(LSA_HANDLE PolicyHandle, PSID AccountSid, PLSA_UNICODE_STRING *UserRights, PULONG CountOfRights)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18003c9f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ca88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ca88`
- `RPCRT4!NdrClientCall3` at `0x18003ca46`
- `RPCRT4!NdrClientCall3` at `0x18003ca46`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003ca6a`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003ca6a`

## pseudocode

```c

```

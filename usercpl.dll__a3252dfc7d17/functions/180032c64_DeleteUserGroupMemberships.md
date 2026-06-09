# _DeleteUserGroupMemberships

- ea: `0x180032c64`
- end: `0x180032d6f`
- name: `_DeleteUserGroupMemberships`
- size: `267`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800343b0`

## callees

- `0x180032c64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032d50`
- `samcli!NetLocalGroupEnum` at `0x180032cc6`
- `samcli!NetLocalGroupEnum` at `0x180032cc6`
- `samcli!NetLocalGroupDelMembers` at `0x180032cf2`
- `samcli!NetLocalGroupDelMembers` at `0x180032cf2`
- `netutils!NetApiBufferFree` at `0x180032d31`
- `netutils!NetApiBufferFree` at `0x180032d31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032d48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032d48`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180032c7b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180032c7b`

## pseudocode

```c

```

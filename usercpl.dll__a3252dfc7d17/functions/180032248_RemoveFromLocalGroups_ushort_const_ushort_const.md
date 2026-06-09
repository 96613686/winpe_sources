# RemoveFromLocalGroups(ushort const *,ushort const *)

- ea: `0x180032248`
- end: `0x18003236c`
- name: `?RemoveFromLocalGroups@@YAJPEBG0@Z`
- size: `292`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002d85c`
- `0x180033bd0`

## callees

- `0x180032248`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18003226a`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18003226a`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800322f7`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800322f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003234f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003234f`
- `samcli!NetLocalGroupEnum` at `0x1800322cd`
- `samcli!NetLocalGroupEnum` at `0x1800322cd`
- `samcli!NetLocalGroupDelMembers` at `0x18003231d`
- `samcli!NetLocalGroupDelMembers` at `0x18003231d`
- `netutils!NetApiBufferFree` at `0x18003233c`
- `netutils!NetApiBufferFree` at `0x18003233c`

## pseudocode

```c

```

# PersistUpdateCommitRequired(_GUID const *,_GUID const &,bool)

- ea: `0x18012ffe8`
- end: `0x1801302f3`
- name: `?PersistUpdateCommitRequired@@YAXPEBU_GUID@@AEBU1@_N@Z`
- size: `779`
- prototype: `void __fastcall(GUID *rguid, GUID *, bool)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180024670`
- `0x180081440`
- `0x1800d9048`

## callees

- `0x18000c6b4`
- `0x18012b618`
- `0x18012d780`
- `0x18012e4dc`
- `0x18012e67c`
- `0x18012ffe8`
- `0x180131a30`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013014f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801302d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18013014f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801302d0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180130180`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180130180`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801301be`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801302b8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801301be`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801302b8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180130026`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180130044`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180130026`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180130044`

## string_xrefs

- `0x1801300d7`: `PersistUpdateCommitRequired: idSrv=%ws, UpdateId=%ws, fRequiresCommit=%u`
- `0x1801301d1`: `PersistUpdateCommitRequired: idSrv=%ws, UpdateId=%ws, fRequiresCommit=%u`

## pseudocode

```c

```

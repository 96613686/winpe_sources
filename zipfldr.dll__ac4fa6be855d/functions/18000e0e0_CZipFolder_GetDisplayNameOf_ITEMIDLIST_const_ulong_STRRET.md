# CZipFolder::GetDisplayNameOf(_ITEMIDLIST const *,ulong,_STRRET *)

- ea: `0x18000e0e0`
- end: `0x18000e2b9`
- name: `?GetDisplayNameOf@CZipFolder@@UEAAJPEFBU_ITEMIDLIST@@KPEAU_STRRET@@@Z`
- size: `473`
- prototype: `int(CZipFolder *__hidden this, const struct _ITEMIDLIST *, unsigned int, struct _STRRET *)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path`

## callees

- `0x18000de14`
- `0x18000e0e0`
- `0x18000ed28`
- `0x18000f5f0`
- `0x180036f50`
- `0x180037958`

## import_xrefs

- `SHELL32!SHGetFileInfoW` at `0x18000e20f`
- `SHELL32!SHGetFileInfoW` at `0x18000e20f`
- `SHELL32!__imp_ILFindLastID` at `0x18000e11e`
- `SHELL32!__imp_ILFindLastID` at `0x18000e11e`
- `SHLWAPI!SHStrDupW` at `0x18000e1b4`
- `SHLWAPI!SHStrDupW` at `0x18000e1b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e276`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e276`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000e186`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000e186`

## pseudocode

```c

```

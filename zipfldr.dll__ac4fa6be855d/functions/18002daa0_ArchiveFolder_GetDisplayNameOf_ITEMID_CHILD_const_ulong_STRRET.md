# ArchiveFolder::GetDisplayNameOf(_ITEMID_CHILD const *,ulong,_STRRET *)

- ea: `0x18002daa0`
- end: `0x18002e0ba`
- name: `?GetDisplayNameOf@ArchiveFolder@@UEAAJPEFBU_ITEMID_CHILD@@KPEAU_STRRET@@@Z`
- size: `1562`
- prototype: `__int64 __fastcall(ArchiveFolder *this, const struct _ITEMID_CHILD *, unsigned int, struct _STRRET *)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path`

## callees

- `0x18000f1c0`
- `0x18000f5f0`
- `0x180010c30`
- `0x180020708`
- `0x18002daa0`
- `0x180030a3c`
- `0x180031e94`
- `0x180036f50`
- `0x180037958`
- `0x180040e04`
- `0x180049660`
- `0x180071010`

## import_xrefs

- `SHELL32!SHBindToParent` at `0x18002db6d`
- `SHELL32!SHBindToParent` at `0x18002db6d`
- `SHELL32!SHGetFileInfoW` at `0x18002df81`
- `SHELL32!SHGetFileInfoW` at `0x18002df81`
- `SHLWAPI!SHStrDupW` at `0x18002e02e`
- `SHLWAPI!SHStrDupW` at `0x18002e02e`
- `SHLWAPI!StrRetToBufW` at `0x18002dd55`
- `SHLWAPI!StrRetToBufW` at `0x18002dd55`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x18002df01`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x18002df01`

## pseudocode

```c

```

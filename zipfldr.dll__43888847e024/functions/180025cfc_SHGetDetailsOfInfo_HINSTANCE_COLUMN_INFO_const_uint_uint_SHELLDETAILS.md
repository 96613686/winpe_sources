# SHGetDetailsOfInfo(HINSTANCE__ *,COLUMN_INFO const *,uint,uint,_SHELLDETAILS *)

- ea: `0x180025cfc`
- end: `0x180025e4d`
- name: `?SHGetDetailsOfInfo@@YAJPEAUHINSTANCE__@@PEBUCOLUMN_INFO@@IIPEAU_SHELLDETAILS@@@Z`
- size: `337`
- prototype: `__int64 __fastcall(HINSTANCE, const struct COLUMN_INFO *, unsigned int, unsigned int, struct _SHELLDETAILS *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180025cc0`
- `0x18004bfa0`

## callees

- `0x180025cfc`
- `0x180036f50`
- `0x180046130`
- `0x180071010`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x180025e09`
- `SHLWAPI!SHStrDupW` at `0x180025e3c`
- `SHLWAPI!SHStrDupW` at `0x180025e09`
- `SHLWAPI!SHStrDupW` at `0x180025e3c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025d78`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180025d78`

## pseudocode

```c

```

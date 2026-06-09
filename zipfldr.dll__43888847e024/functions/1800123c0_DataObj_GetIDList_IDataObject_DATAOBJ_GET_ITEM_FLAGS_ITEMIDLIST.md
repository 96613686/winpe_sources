# DataObj_GetIDList(IDataObject *,DATAOBJ_GET_ITEM_FLAGS,_ITEMIDLIST * *)

- ea: `0x1800123c0`
- end: `0x180012544`
- name: `?DataObj_GetIDList@@YAJPEAUIDataObject@@W4DATAOBJ_GET_ITEM_FLAGS@@PEAPEFAU_ITEMIDLIST@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(struct IDataObject *, enum DATAOBJ_GET_ITEM_FLAGS, struct _ITEMIDLIST **)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180012340`
- `0x180044d04`

## callees

- `0x1800123c0`
- `0x180012994`
- `0x180012c38`
- `0x18002a3bc`
- `0x180035110`
- `0x180036f50`
- `0x180044554`
- `0x18006e9a0`

## import_xrefs

- `SHELL32!SHParseDisplayName` at `0x1800124c1`
- `SHELL32!SHParseDisplayName` at `0x18001250e`
- `SHELL32!SHParseDisplayName` at `0x1800124c1`
- `SHELL32!SHParseDisplayName` at `0x18001250e`
- `SHELL32!__imp_ILCombine` at `0x180012453`
- `SHELL32!__imp_ILCombine` at `0x180012453`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x1800124f2`
- `SHLWAPI!__imp_SHAnsiToUnicode` at `0x1800124f2`
- `KERNEL32!GlobalUnlock` at `0x180012482`
- `KERNEL32!GlobalUnlock` at `0x180012482`
- `ole32!ReleaseStgMedium` at `0x18001248d`
- `ole32!ReleaseStgMedium` at `0x18001248d`

## pseudocode

```c

```

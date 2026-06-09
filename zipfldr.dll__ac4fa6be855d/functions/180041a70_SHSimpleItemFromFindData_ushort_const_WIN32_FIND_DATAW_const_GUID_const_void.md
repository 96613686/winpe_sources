# SHSimpleItemFromFindData(ushort const *,_WIN32_FIND_DATAW const *,_GUID const &,void * *)

- ea: `0x180041a70`
- end: `0x180041b2b`
- name: `?SHSimpleItemFromFindData@@YAJPEBGPEBU_WIN32_FIND_DATAW@@AEBU_GUID@@PEAPEAX@Z`
- size: `187`
- prototype: `__int64 __fastcall(PCWSTR pszName, const struct _WIN32_FIND_DATAW *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180041050`

## callees

- `0x18000cb04`
- `0x180036f50`
- `0x180041a70`
- `0x180071010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x180041af2`
- `SHELL32!SHCreateItemFromIDList` at `0x180041af2`
- `SHELL32!SHParseDisplayName` at `0x180041ac6`
- `SHELL32!SHParseDisplayName` at `0x180041ac6`
- `SHELL32!__imp_ILFree` at `0x180041aff`
- `SHELL32!__imp_ILFree` at `0x180041aff`

## pseudocode

```c

```

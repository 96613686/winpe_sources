# CComSxSCatalog::GetClassInfoW(ulong,IUserToken *,_GUID const &,_GUID const &,void * *,void *)

- ea: `0x1800d5520`
- end: `0x1800d57b2`
- name: `?GetClassInfoW@CComSxSCatalog@@UEAAJKPEAUIUserToken@@AEBU_GUID@@1PEAPEAXPEAX@Z`
- size: `658`
- prototype: `int(CComSxSCatalog *__hidden this, unsigned int, struct IUserToken *, const struct _GUID *, const struct _GUID *, void **, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d5370`

## callees

- `0x18001a374`
- `0x180034260`
- `0x180074d98`
- `0x180095c0c`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x1800d5520`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d55a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d55a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d563e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d563e`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionGuid` at `0x1800d5595`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionGuid` at `0x1800d5595`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800d56c7`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800d570c`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800d5724`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800d56c7`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800d570c`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800d5724`
- `api-ms-win-core-sidebyside-l1-1-0!AddRefActCtx` at `0x1800d569f`
- `api-ms-win-core-sidebyside-l1-1-0!AddRefActCtx` at `0x1800d569f`

## string_xrefs

- `0x1800d577b`: `CLSID:%ws %!HRESULT!`
- `0x1800d5768`: `CComSxSCatalog::GetClassInfoW`
- `0x1800d5774`: `onecore\com\combase\catalog\sxscat.cxx`

## pseudocode

```c

```

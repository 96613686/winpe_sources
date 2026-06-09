# CComSxSCatalog::GetClassInfoW(ulong,IUserToken *,_GUID const &,_GUID const &,void * *,void *)

- ea: `0x1800ceda0`
- end: `0x1800cf004`
- name: `?GetClassInfoW@CComSxSCatalog@@UEAAJKPEAUIUserToken@@AEBU_GUID@@1PEAPEAXPEAX@Z`
- size: `612`
- prototype: `int(CComSxSCatalog *__hidden this, unsigned int, struct IUserToken *, const struct _GUID *, const struct _GUID *, void **, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cec10`

## callees

- `0x180016160`
- `0x180034540`
- `0x180070740`
- `0x18008e98c`
- `0x1800b27e0`
- `0x1800b3128`
- `0x1800ceda0`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cee1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cee1f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ceeb2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800ceeb2`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionGuid` at `0x1800cee15`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionGuid` at `0x1800cee15`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800cef2f`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800cef6b`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800cef7d`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800cef2f`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800cef6b`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x1800cef7d`
- `api-ms-win-core-sidebyside-l1-1-0!AddRefActCtx` at `0x1800cef0d`
- `api-ms-win-core-sidebyside-l1-1-0!AddRefActCtx` at `0x1800cef0d`

## string_xrefs

- `0x1800cefce`: `CLSID:%ws %!HRESULT!`
- `0x1800cefbb`: `CComSxSCatalog::GetClassInfoW`
- `0x1800cefc7`: `onecore\com\combase\catalog\sxscat.cxx`

## pseudocode

```c

```

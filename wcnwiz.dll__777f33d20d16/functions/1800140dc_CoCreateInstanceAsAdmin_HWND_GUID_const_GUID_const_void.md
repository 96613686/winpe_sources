# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x1800140dc`
- end: `0x1800141cb`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800144e4`

## callees

- `0x180001820`
- `0x1800140dc`
- `0x180015d28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180014138`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180014138`
- `ole32!CoGetObject` at `0x1800141a1`
- `ole32!CoGetObject` at `0x1800141a1`

## pseudocode

```c

```

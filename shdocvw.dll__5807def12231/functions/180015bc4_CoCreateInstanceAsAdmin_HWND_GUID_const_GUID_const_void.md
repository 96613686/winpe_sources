# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x180015bc4`
- end: `0x180015cb3`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800188b0`

## callees

- `0x180008320`
- `0x18000bf78`
- `0x180015bc4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180015c20`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180015c20`
- `ole32!CoGetObject` at `0x180015c89`
- `ole32!CoGetObject` at `0x180015c89`

## pseudocode

```c

```

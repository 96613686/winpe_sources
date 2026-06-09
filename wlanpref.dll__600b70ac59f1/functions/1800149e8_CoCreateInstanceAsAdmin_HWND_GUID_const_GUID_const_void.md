# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x1800149e8`
- end: `0x180014ad7`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014ef8`

## callees

- `0x1800149e8`
- `0x1800153dc`
- `0x18002d840`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180014a44`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180014a44`
- `ole32!CoGetObject` at `0x180014aad`
- `ole32!CoGetObject` at `0x180014aad`

## pseudocode

```c

```

# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x18001cf40`
- end: `0x18001d02f`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `239`
- prototype: `int(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001bf74`

## callees

- `0x180008a0c`
- `0x18001cf40`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001cf9c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001cf9c`
- `ole32!CoGetObject` at `0x18001d005`
- `ole32!CoGetObject` at `0x18001d005`

## pseudocode

```c

```

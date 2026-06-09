# CoCreateInstanceElevated(HWND__ *,_GUID const &,ushort const *,_GUID const &,void * *)

- ea: `0x180014ae0`
- end: `0x180014bdf`
- name: `?CoCreateInstanceElevated@@YAJPEAUHWND__@@AEBU_GUID@@PEBG1PEAPEAX@Z`
- size: `255`
- prototype: `__int64 __fastcall(HWND, const struct _GUID *, const unsigned __int16 *, const struct _GUID *, void **ppv)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014ef8`

## callees

- `0x180014ae0`
- `0x1800153dc`
- `0x18002d840`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180014b40`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180014b40`
- `ole32!CoGetObject` at `0x180014bb5`
- `ole32!CoGetObject` at `0x180014bb5`

## pseudocode

```c

```

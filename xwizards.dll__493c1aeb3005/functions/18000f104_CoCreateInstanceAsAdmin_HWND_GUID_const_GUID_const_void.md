# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x18000f104`
- end: `0x18000f1e2`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `222`
- prototype: `HRESULT __fastcall(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f024`

## callees

- `0x18000f104`
- `0x18000f1e8`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f15c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f15c`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x18000f1c1`
- `ext-ms-win-ole32-bindctx-l1-1-0!CoGetObject` at `0x18000f1c1`

## pseudocode

```c

```

# CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x180027238`
- end: `0x180027316`
- name: `?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `222`
- prototype: `HRESULT __fastcall(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180027544`

## callees

- `0x180005cc0`
- `0x1800095c0`
- `0x180027238`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180027290`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180027290`
- `ole32!CoGetObject` at `0x1800272f5`
- `ole32!CoGetObject` at `0x1800272f5`

## pseudocode

```c

```

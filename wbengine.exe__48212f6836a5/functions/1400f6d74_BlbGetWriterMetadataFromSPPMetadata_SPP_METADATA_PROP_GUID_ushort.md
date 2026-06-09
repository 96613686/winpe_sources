# BlbGetWriterMetadataFromSPPMetadata(_SPP_METADATA_PROP *,_GUID,ushort * *)

- ea: `0x1400f6d74`
- end: `0x1400f7021`
- name: `?BlbGetWriterMetadataFromSPPMetadata@@YAJPEAU_SPP_METADATA_PROP@@U_GUID@@PEAPEAG@Z`
- size: `685`
- prototype: `__int64 __fastcall(struct _SPP_METADATA_PROP *, struct _GUID *__struct_ptr, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x14000d9c0`
- `0x14000ed9c`
- `0x140078f88`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x1400889f0`
- `0x1400f6d74`
- `0x140134cc6`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400f6f8a`
- `ole32!CoTaskMemFree` at `0x1400f6f8a`
- `OLEAUT32!__imp_SysAllocString` at `0x1400f6e7a`
- `OLEAUT32!__imp_SysAllocString` at `0x1400f6e7a`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f6e6c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f6eac`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f6fa1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f6fc5`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f6e6c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f6eac`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f6fa1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400f6fc5`
- `VSSAPI!CreateVssExamineWriterMetadataInternal` at `0x1400f6e93`
- `VSSAPI!CreateVssExamineWriterMetadataInternal` at `0x1400f6e93`

## string_xrefs

- `0x1400f6e22`: `pwszWriterMetaData`

## pseudocode

```c

```

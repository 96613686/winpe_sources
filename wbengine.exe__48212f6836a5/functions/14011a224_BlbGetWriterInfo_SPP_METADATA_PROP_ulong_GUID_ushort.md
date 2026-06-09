# BlbGetWriterInfo(_SPP_METADATA_PROP *,ulong,_GUID *,ushort * *)

- ea: `0x14011a224`
- end: `0x14011a487`
- name: `?BlbGetWriterInfo@@YAJPEAU_SPP_METADATA_PROP@@KPEAU_GUID@@PEAPEAG@Z`
- size: `611`
- prototype: `__int64 __fastcall(struct _SPP_METADATA_PROP *, unsigned int, struct _GUID *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x14002a410`
- `0x14003be8c`
- `0x1400fbb90`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000cbcc`
- `0x14011a224`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x14011a37e`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14011a3d0`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14011a37e`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14011a3d0`
- `KERNEL32!GetLastError` at `0x14011a38b`
- `KERNEL32!GetLastError` at `0x14011a38b`
- `ole32!CoTaskMemFree` at `0x14011a42b`
- `ole32!CoTaskMemFree` at `0x14011a42b`
- `OLEAUT32!__imp_SysAllocString` at `0x14011a309`
- `OLEAUT32!__imp_SysAllocString` at `0x14011a309`
- `OLEAUT32!__imp_SysFreeString` at `0x14011a3f2`
- `OLEAUT32!__imp_SysFreeString` at `0x14011a408`
- `OLEAUT32!__imp_SysFreeString` at `0x14011a3f2`
- `OLEAUT32!__imp_SysFreeString` at `0x14011a408`
- `VSSAPI!CreateVssExamineWriterMetadataInternal` at `0x14011a328`
- `VSSAPI!CreateVssExamineWriterMetadataInternal` at `0x14011a328`

## string_xrefs

- `0x14011a2a0`: `base\stor\blb\engine\blbengutils\blbwriterutils.cpp`
- `0x14011a2bd`: `base\stor\blb\engine\blbengutils\blbwriterutils.cpp`
- `0x14011a2b1`: `pguidWriterId`

## pseudocode

```c

```

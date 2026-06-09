# FederatedDownloadJob::GetJobServiceId(IDownloadJob *,_GUID *)

- ea: `0x180014f3c`
- end: `0x180015020`
- name: `?GetJobServiceId@FederatedDownloadJob@@CAJPEAUIDownloadJob@@PEAU_GUID@@@Z`
- size: `228`
- prototype: `__int64 __fastcall(struct IDownloadJob *, struct _GUID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800141ec`
- `0x180062e10`

## callees

- `0x180006ac4`
- `0x180007ecc`
- `0x180014f3c`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x180014fc9`
- `RPCRT4!UuidFromStringW` at `0x180014fc9`
- `OLEAUT32!__imp_VariantInit` at `0x180014f6d`
- `OLEAUT32!__imp_VariantInit` at `0x180014f79`
- `OLEAUT32!__imp_VariantInit` at `0x180014f6d`
- `OLEAUT32!__imp_VariantInit` at `0x180014f79`
- `OLEAUT32!__imp_VariantClear` at `0x180015000`
- `OLEAUT32!__imp_VariantClear` at `0x180015000`

## string_xrefs

- `0x180014fac`: `C:\__w\1\s\src\Client\comapi\FederatedDownloadJob.cpp`
- `0x180014fdb`: `C:\__w\1\s\src\Client\comapi\FederatedDownloadJob.cpp`

## pseudocode

```c

```

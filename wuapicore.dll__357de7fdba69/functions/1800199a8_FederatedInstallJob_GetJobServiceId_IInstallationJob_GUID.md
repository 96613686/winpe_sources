# FederatedInstallJob::GetJobServiceId(IInstallationJob *,_GUID *)

- ea: `0x1800199a8`
- end: `0x180019a8b`
- name: `?GetJobServiceId@FederatedInstallJob@@CAJPEAUIInstallationJob@@PEAU_GUID@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(struct IInstallationJob *, struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800187c4`
- `0x180027350`

## callees

- `0x180006ac4`
- `0x1800199a8`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x180019a24`
- `RPCRT4!UuidFromStringW` at `0x180019a24`
- `OLEAUT32!__imp_VariantInit` at `0x1800199d9`
- `OLEAUT32!__imp_VariantInit` at `0x1800199e5`
- `OLEAUT32!__imp_VariantInit` at `0x1800199d9`
- `OLEAUT32!__imp_VariantInit` at `0x1800199e5`
- `OLEAUT32!__imp_VariantClear` at `0x180019a6b`
- `OLEAUT32!__imp_VariantClear` at `0x180019a6b`

## string_xrefs

- `0x180019a48`: `C:\__w\1\s\src\Client\comapi\FederatedInstallJob.cpp`

## pseudocode

```c

```

# CallerIdentity::GetPackageFamilyNameFromProcess(void *,ushort * *)

- ea: `0x1800e0d10`
- end: `0x1800e0df1`
- name: `?GetPackageFamilyNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z`
- size: `225`
- prototype: `__int64 __fastcall(HANDLE hProcess, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800e0b04`

## callees

- `0x18001b950`
- `0x1800e0d10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e0d72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e0dd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e0d72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e0dd5`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800e0d39`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800e0dab`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800e0d39`
- `api-ms-win-appmodel-runtime-l1-1-0!GetPackageFamilyName` at `0x1800e0dab`

## pseudocode

```c

```

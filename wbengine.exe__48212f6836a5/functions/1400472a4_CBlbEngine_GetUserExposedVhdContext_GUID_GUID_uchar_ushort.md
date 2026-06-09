# CBlbEngine::GetUserExposedVhdContext(_GUID,_GUID,uchar *,ushort * *)

- ea: `0x1400472a4`
- end: `0x140047801`
- name: `?GetUserExposedVhdContext@CBlbEngine@@QEAAJU_GUID@@0PEAEPEAPEAG@Z`
- size: `1373`
- prototype: `int(CBlbEngine *__hidden this, struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, unsigned __int8 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task`

## callers

- `0x14004a690`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14000be04`
- `0x14000bfd8`
- `0x14001358c`
- `0x1400142d8`
- `0x140014448`
- `0x1400472a4`
- `0x14008d550`
- `0x14008f1b8`
- `0x140134cc6`
- `0x140134d20`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1400477a9`
- `ole32!CoTaskMemFree` at `0x1400477a9`
- `OLEAUT32!__imp_SysFreeString` at `0x14004743f`
- `OLEAUT32!__imp_SysFreeString` at `0x140047453`
- `OLEAUT32!__imp_SysFreeString` at `0x14004762b`
- `OLEAUT32!__imp_SysFreeString` at `0x1400476cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1400476dd`
- `OLEAUT32!__imp_SysFreeString` at `0x14004777c`
- `OLEAUT32!__imp_SysFreeString` at `0x140047794`
- `OLEAUT32!__imp_SysFreeString` at `0x14004743f`
- `OLEAUT32!__imp_SysFreeString` at `0x140047453`
- `OLEAUT32!__imp_SysFreeString` at `0x14004762b`
- `OLEAUT32!__imp_SysFreeString` at `0x1400476cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1400476dd`
- `OLEAUT32!__imp_SysFreeString` at `0x14004777c`
- `OLEAUT32!__imp_SysFreeString` at `0x140047794`

## string_xrefs

- `0x14004733d`: `base\stor\blb\engine\service\engine.cpp`
- `0x1400473a7`: `pwszMountedPath != NULL`

## pseudocode

```c

```

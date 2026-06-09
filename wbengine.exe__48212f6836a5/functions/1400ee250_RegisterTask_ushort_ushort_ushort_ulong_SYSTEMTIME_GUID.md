# RegisterTask(ushort *,ushort *,ushort *,ulong,_SYSTEMTIME *,_GUID)

- ea: `0x1400ee250`
- end: `0x1400ef325`
- name: `?RegisterTask@@YAJPEAG00KPEAU_SYSTEMTIME@@U_GUID@@@Z`
- size: `4309`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, struct _SYSTEMTIME *, struct _GUID *Buf1)`
- caller_count: `1`
- callee_count: `21`
- tags: `service_task`

## callers

- `0x1400502e0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14001358c`
- `0x140014200`
- `0x140014fd8`
- `0x140015010`
- `0x14006a01c`
- `0x14006a044`
- `0x14007007c`
- `0x1400ec784`
- `0x1400ec7d0`
- `0x1400ec7f4`
- `0x1400ec818`
- `0x1400ecc38`
- `0x1400ece3c`
- `0x1400ecfc0`
- `0x1400ee250`
- `0x140134cc6`
- `0x140134d20`
- `0x140137010`

## import_xrefs

- `msvcrt!_wgetenv` at `0x1400ee534`
- `msvcrt!_wgetenv` at `0x1400ee572`
- `msvcrt!_wgetenv` at `0x1400ee534`
- `msvcrt!_wgetenv` at `0x1400ee572`
- `ole32!CoCreateInstance` at `0x1400ee3e1`
- `ole32!CoCreateInstance` at `0x1400ee3e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400ef2b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400ef2ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1400ef2c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1400ef2cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1400ef2d5`
- `OLEAUT32!__imp_SysFreeString` at `0x1400ef2de`
- `OLEAUT32!__imp_SysFreeString` at `0x1400ef2b1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400ef2ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1400ef2c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1400ef2cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1400ef2d5`
- `OLEAUT32!__imp_SysFreeString` at `0x1400ef2de`
- `OLEAUT32!__imp_VariantInit` at `0x1400ee378`
- `OLEAUT32!__imp_VariantInit` at `0x1400ee382`
- `OLEAUT32!__imp_VariantInit` at `0x1400ef01b`
- `OLEAUT32!__imp_VariantInit` at `0x1400ef05c`
- `OLEAUT32!__imp_VariantInit` at `0x1400ee378`
- `OLEAUT32!__imp_VariantInit` at `0x1400ee382`
- `OLEAUT32!__imp_VariantInit` at `0x1400ef01b`
- `OLEAUT32!__imp_VariantInit` at `0x1400ef05c`

## string_xrefs

- `0x1400ee33f`: `guidTemplateId != GUID_NULL`
- `0x1400ee846`: `%windir%\System32\wbadmin.exe`
- `0x1400ee903`: `start backup -templateId:{%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x} -quiet`

## pseudocode

```c

```

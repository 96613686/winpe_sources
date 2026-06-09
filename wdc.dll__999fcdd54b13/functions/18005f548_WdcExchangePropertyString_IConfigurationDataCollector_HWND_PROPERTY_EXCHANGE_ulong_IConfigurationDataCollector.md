# WdcExchangePropertyString<IConfigurationDataCollector>(HWND__ *,PROPERTY_EXCHANGE,ulong,IConfigurationDataCollector *,long (IConfigurationDataCollector::*)(ushort * *),long (IConfigurationDataCollector::*)(ushort *),WdcValidation *,ushort *,ulong)

- ea: `0x18005f548`
- end: `0x18005f6b4`
- name: `??$WdcExchangePropertyString@UIConfigurationDataCollector@@@@YAJPEAUHWND__@@W4PROPERTY_EXCHANGE@@KPEAUIConfigurationDataCollector@@P82@EAAJPEAPEAG@ZP82@EAAJPEAG@ZPEAVWdcValidation@@5K@Z`
- size: `364`
- prototype: `__int64 __fastcall(HWND, __int16, __int64, __int64, WCHAR *, int, WdcValidation *, LPWSTR lpString)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180061560`

## callees

- `0x18000b854`
- `0x180026490`
- `0x180054f40`
- `0x18005f548`
- `0x18005fc88`
- `0x180069170`
- `0x18006a034`

## import_xrefs

- `USER32!GetWindowTextW` at `0x18005f5e4`
- `USER32!GetWindowTextW` at `0x18005f5e4`
- `USER32!EnableWindow` at `0x18005f5b7`
- `USER32!EnableWindow` at `0x18005f5b7`
- `USER32!SetWindowTextW` at `0x18005f68a`
- `USER32!SetWindowTextW` at `0x18005f68a`
- `USER32!GetDlgItem` at `0x18005f56d`
- `USER32!GetDlgItem` at `0x18005f56d`
- `OLEAUT32!__imp_SysAllocString` at `0x18005f5f2`
- `OLEAUT32!__imp_SysAllocString` at `0x18005f5f2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f69d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f69d`

## pseudocode

```c

```

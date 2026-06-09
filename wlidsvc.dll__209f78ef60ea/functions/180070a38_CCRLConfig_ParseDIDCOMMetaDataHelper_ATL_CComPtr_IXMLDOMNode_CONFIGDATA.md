# CCRLConfig::ParseDIDCOMMetaDataHelper(ATL::CComPtr<IXMLDOMNode> &,CONFIGDATA *)

- ea: `0x180070a38`
- end: `0x180070d9d`
- name: `?ParseDIDCOMMetaDataHelper@CCRLConfig@@AEAAJAEAV?$CComPtr@UIXMLDOMNode@@@ATL@@PEAUCONFIGDATA@@@Z`
- size: `869`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180070560`

## callees

- `0x18000c050`
- `0x18000d89c`
- `0x18000ed3c`
- `0x1800151c4`
- `0x180015860`
- `0x180018f80`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180032684`
- `0x180034728`
- `0x180039ee8`
- `0x1800406a8`
- `0x180044598`
- `0x18006e110`
- `0x180070a38`
- `0x180128010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180070af0`
- `OLEAUT32!__imp_SysFreeString` at `0x180070b80`
- `OLEAUT32!__imp_SysFreeString` at `0x180070bc7`
- `OLEAUT32!__imp_SysFreeString` at `0x180070d6f`
- `OLEAUT32!__imp_SysFreeString` at `0x180070af0`
- `OLEAUT32!__imp_SysFreeString` at `0x180070b80`
- `OLEAUT32!__imp_SysFreeString` at `0x180070bc7`
- `OLEAUT32!__imp_SysFreeString` at `0x180070d6f`
- `OLEAUT32!__imp_SysStringLen` at `0x180070b30`
- `OLEAUT32!__imp_SysStringLen` at `0x180070bfb`
- `OLEAUT32!__imp_SysStringLen` at `0x180070b30`
- `OLEAUT32!__imp_SysStringLen` at `0x180070bfb`

## string_xrefs

- `0x180070aa9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\configuration.cpp`
- `0x180070a7a`: `CCRLConfig::ParseDIDCOMMetaDataHelper`
- `0x180070cb5`: `hr = ParseDIDConfigBoolean<DeviceProtocolMetaData>(pNode, CComBSTR(c_szDeviceLogical), true, false, cCLSID, &(DeviceProtocolMetaData::SetIsLogical))`
- `0x180070c5d`: `hr = ParseDIDConfigBoolean<DeviceProtocolMetaData>(pNode, CComBSTR(c_szDeviceSystem), true, false, cCLSID, &(DeviceProtocolMetaData::SetIsSystem))`

## pseudocode

```c

```

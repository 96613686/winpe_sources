# CEnumDevicesRequest::ParseResponseBody(IXMLDOMNode *)

- ea: `0x1800d3620`
- end: `0x1800d39a1`
- name: `?ParseResponseBody@CEnumDevicesRequest@@MEAAJPEAUIXMLDOMNode@@@Z`
- size: `897`
- prototype: `__int64 __fastcall(CEnumDevicesRequest *__hidden this, struct IXMLDOMNode *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x180015860`
- `0x180039ee8`
- `0x1800406a8`
- `0x180044598`
- `0x1800469b8`
- `0x1800a716c`
- `0x1800d0d14`
- `0x1800d3620`
- `0x180128010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800d36a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d370c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d37e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d3890`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d38a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d3951`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d395c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d36a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d370c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d37e2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d3890`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d38a2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d3951`
- `OLEAUT32!__imp_SysFreeString` at `0x1800d395c`
- `OLEAUT32!__imp_SysStringLen` at `0x1800d3787`
- `OLEAUT32!__imp_SysStringLen` at `0x1800d3787`

## string_xrefs

- `0x1800d3940`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800d3716`: `SUCCEEDED(hr = pResponse->selectNodes(CComBSTR("ps:Devices/ps:Device"), &pDevices)) && hr != S_FALSE`
- `0x1800d390f`: `SUCCEEDED(hr = pDevice->selectSingleNode(CComBSTR(L"@FriendlyName"), &pNameAttr)) && hr != S_FALSE`

## pseudocode

```c

```

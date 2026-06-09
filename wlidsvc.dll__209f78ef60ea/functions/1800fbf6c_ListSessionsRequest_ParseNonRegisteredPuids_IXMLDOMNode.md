# ListSessionsRequest::ParseNonRegisteredPuids(IXMLDOMNode *)

- ea: `0x1800fbf6c`
- end: `0x1800fc1c9`
- name: `?ParseNonRegisteredPuids@ListSessionsRequest@@AEAAJPEAUIXMLDOMNode@@@Z`
- size: `605`
- prototype: `__int64 __fastcall(ListSessionsRequest *__hidden this, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800fc1d0`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x180015860`
- `0x18001c688`
- `0x1800406a8`
- `0x1800469b8`
- `0x1800fbf6c`
- `0x180128010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800fbfd0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc014`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc0f9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc10b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc14b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc1b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fbfd0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc014`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc0f9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc10b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc14b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc1b6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800fc0d1`
- `OLEAUT32!__imp_SysStringLen` at `0x1800fc0d1`

## string_xrefs

- `0x1800fc095`: `hr = PPCRL_RESPONSE_BADXML`
- `0x1800fc129`: `hr = PPCRL_RESPONSE_BADXML`
- `0x1800fc03a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\listsessionsrequest.cpp`
- `0x1800fc1a5`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\listsessionsrequest.cpp`
- `0x1800fc01e`: `hr = pNode->selectNodes(CComBSTR("ps:NotRegistered/ps:PUID"), &pNotRegisteredPuids)`

## pseudocode

```c

```

# ListSessionsRequest::ParseResponse(char const *,ulong,ulong &)

- ea: `0x1800fc1d0`
- end: `0x1800fc5c1`
- name: `?ParseResponse@ListSessionsRequest@@UEAAJPEBDKAEAK@Z`
- size: `1009`
- prototype: `__int64 __fastcall(ListSessionsRequest *__hidden this, const char *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x180015430`
- `0x18001686c`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001b330`
- `0x180021b28`
- `0x18002eed0`
- `0x1800406a8`
- `0x180044408`
- `0x1800469b8`
- `0x18005dc64`
- `0x180060384`
- `0x1800d0824`
- `0x1800fbf6c`
- `0x1800fc1d0`
- `0x1800fc5c8`
- `0x180108258`
- `0x180128010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800fc349`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc3bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc3ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc440`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc4c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc349`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc3bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc3ec`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc440`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fc4c3`
- `OLEAUT32!__imp_VariantClear` at `0x1800fc5a9`
- `OLEAUT32!__imp_VariantClear` at `0x1800fc5a9`

## string_xrefs

- `0x1800fc209`: ` xmlns:ds="http://www.w3.org/2000/09/xmldsig#" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:wssc="http://schemas.xmlsoap.org/ws/2005/02/sc" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" xmlns:S="http://www.w3.org/2003/05/soap-envel`
- `0x1800fc2f8`: `hr = CreateDOM(response, k_cvPPCRLSTSNamespaces, pXmlResponse)`
- `0x1800fc263`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\listsessionsrequest.cpp`
- `0x1800fc353`: `hr = pXmlResponse->selectSingleNode(CComBSTR(c_szListSessionsSuccessResponsePath), &pNode)`
- `0x1800fc44a`: `hr = pNode->selectSingleNode(CComBSTR(c_szListSessionsErrorcodePath), &pErrorNode)`
- `0x1800fc3c7`: `hr = pXmlResponse->selectSingleNode(CComBSTR(c_szListSessionsFailureResponsePath), &pNode)`
- `0x1800fc4cd`: `hr = ParseNumericHResult(pNode, CComBSTR(c_szListSessionsErrorSubcodePath), hrSubError)`

## pseudocode

```c

```

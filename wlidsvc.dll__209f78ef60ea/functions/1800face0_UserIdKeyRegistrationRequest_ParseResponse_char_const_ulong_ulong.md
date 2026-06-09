# UserIdKeyRegistrationRequest::ParseResponse(char const *,ulong,ulong &)

- ea: `0x1800face0`
- end: `0x1800fb059`
- name: `?ParseResponse@UserIdKeyRegistrationRequest@@UEAAJPEBDKAEAK@Z`
- size: `889`
- prototype: `__int64 __fastcall(UserIdKeyRegistrationRequest *__hidden this, const char *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009e98`
- `0x18000a36c`
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
- `0x1800face0`
- `0x180108258`
- `0x180128010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800fae93`
- `OLEAUT32!__imp_SysFreeString` at `0x1800faef7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800faf83`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fb041`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fae93`
- `OLEAUT32!__imp_SysFreeString` at `0x1800faef7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800faf83`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fb041`
- `OLEAUT32!__imp_VariantClear` at `0x1800fb036`
- `OLEAUT32!__imp_VariantClear` at `0x1800fb036`

## string_xrefs

- `0x1800fad1a`: ` xmlns:ds="http://www.w3.org/2000/09/xmldsig#" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:wssc="http://schemas.xmlsoap.org/ws/2005/02/sc" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" xmlns:S="http://www.w3.org/2003/05/soap-envel`
- `0x1800fae34`: `hr = CreateDOM(response, k_cvPPCRLSTSNamespaces, pXmlResponse)`
- `0x1800fad7c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\useridkeyregistrationrequest.cpp`
- `0x1800fae9d`: `hr = pXmlResponse->selectSingleNode(CComBSTR(c_szUserIdKeyRegistrationResponsePath), &pNode)`
- `0x1800faf8d`: `hr = ParseNumericHResult(pNode, CComBSTR(c_szUserIdKeyRegistrationErrorSubcodePath), _serverSubError)`
- `0x1800faf01`: `hr = pNode->selectSingleNode(CComBSTR(c_szUserIdKeyRegistrationErrorcodePath), &pErrorNode)`

## pseudocode

```c

```

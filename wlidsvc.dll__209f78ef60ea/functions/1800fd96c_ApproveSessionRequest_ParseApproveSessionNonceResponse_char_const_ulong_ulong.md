# ApproveSessionRequest::ParseApproveSessionNonceResponse(char const *,ulong,ulong &)

- ea: `0x1800fd96c`
- end: `0x1800fdd80`
- name: `?ParseApproveSessionNonceResponse@ApproveSessionRequest@@AEAAJPEBDKAEAK@Z`
- size: `1044`
- prototype: `__int64 __fastcall(ApproveSessionRequest *__hidden this, const char *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800fe1d0`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x180015430`
- `0x180015860`
- `0x18001686c`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001b330`
- `0x18002eed0`
- `0x1800406a8`
- `0x180044408`
- `0x1800469b8`
- `0x18005dc64`
- `0x180060384`
- `0x1800d0824`
- `0x1800fd96c`
- `0x180108258`
- `0x180128010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800fdb0e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fdbb4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fdc1b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fdca7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fdd5d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fdd68`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fdb0e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fdbb4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fdc1b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fdca7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fdd5d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800fdd68`
- `OLEAUT32!__imp_VariantClear` at `0x1800fdd52`
- `OLEAUT32!__imp_VariantClear` at `0x1800fdd52`

## string_xrefs

- `0x1800fd9b5`: ` xmlns:ds="http://www.w3.org/2000/09/xmldsig#" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:wssc="http://schemas.xmlsoap.org/ws/2005/02/sc" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" xmlns:S="http://www.w3.org/2003/05/soap-envel`
- `0x1800fdaaf`: `hr = CreateDOM(response, k_cvPPCRLSTSNamespaces, pXmlResponse)`
- `0x1800fda1f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\approvesessionrequest.cpp`
- `0x1800fdbbe`: `hr = pXmlResponse->selectSingleNode(CComBSTR(c_szApproveSessionResponsePath), &pNode)`
- `0x1800fdcb1`: `hr = ParseNumericHResult(pNode, CComBSTR(c_szApproveSessionErrorSubcodePath), hrSubError)`
- `0x1800fdc25`: `hr = pNode->selectSingleNode(CComBSTR(c_szApproveSessionErrorcodePath), &pErrorNode)`
- `0x1800fdb18`: `hr = pXmlResponse->selectSingleNode(CComBSTR(c_szApproveSessionNonceResponsePath), &pNonceNode)`

## pseudocode

```c

```

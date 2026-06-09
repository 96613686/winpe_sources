# ManageApproverRequest::ParseResponse(char const *,ulong,ulong &)

- ea: `0x1800f2e20`
- end: `0x1800f321c`
- name: `?ParseResponse@ManageApproverRequest@@UEAAJPEBDKAEAK@Z`
- size: `1020`
- prototype: `__int64 __fastcall(ManageApproverRequest *__hidden this, const char *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `20`
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
- `0x1800f2e20`
- `0x180108258`
- `0x180128010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800f2fbf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f3023`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f30bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f314b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f3204`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f2fbf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f3023`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f30bf`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f314b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800f3204`
- `OLEAUT32!__imp_VariantClear` at `0x1800f31f9`
- `OLEAUT32!__imp_VariantClear` at `0x1800f31f9`

## string_xrefs

- `0x1800f2e61`: ` xmlns:ds="http://www.w3.org/2000/09/xmldsig#" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:wssc="http://schemas.xmlsoap.org/ws/2005/02/sc" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" xmlns:S="http://www.w3.org/2003/05/soap-envel`
- `0x1800f2ecb`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\manageapproverrequest.cpp`
- `0x1800f2fc9`: `hr = pXmlResponse->selectSingleNode(CComBSTR(c_szManageApproverResponsePath), &pNode)`
- `0x1800f2f60`: `hr = CreateDOM(response, k_cvPPCRLSTSNamespaces, pXmlResponse)`
- `0x1800f302d`: `hr = pNode->selectSingleNode(CComBSTR(c_szManageApproverTOTPSharedKeyPath), &pTotpSharedKey)`
- `0x1800f30c9`: `hr = pNode->selectSingleNode(CComBSTR(c_szManageApproverErrorcodePath), &pErrorNode)`
- `0x1800f3155`: `hr = ParseNumericHResult(pNode, CComBSTR(c_szManageApproverErrorSubcodePath), hrSubError)`

## pseudocode

```c

```

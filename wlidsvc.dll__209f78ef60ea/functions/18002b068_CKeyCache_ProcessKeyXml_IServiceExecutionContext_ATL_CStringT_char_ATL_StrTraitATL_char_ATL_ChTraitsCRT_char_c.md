# CKeyCache::ProcessKeyXml(IServiceExecutionContext *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &)

- ea: `0x18002b068`
- end: `0x18002b2b4`
- name: `?ProcessKeyXml@CKeyCache@@QEAAJPEAVIServiceExecutionContext@@AEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z`
- size: `588`
- prototype: `__int64 __fastcall(CKeyCache *this, struct IServiceExecutionContext *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800efc0c`

## callees

- `0x18000c050`
- `0x180014a20`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18002b068`
- `0x18002b370`
- `0x18002b4ec`
- `0x18007c408`
- `0x1800a3b60`
- `0x180108d20`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002b196`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002b196`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b0d7`
- `OLEAUT32!__imp_SysAllocString` at `0x18002b0d7`
- `OLEAUT32!__imp_VariantClear` at `0x18002b0c0`
- `OLEAUT32!__imp_VariantClear` at `0x18002b260`
- `OLEAUT32!__imp_VariantClear` at `0x18002b0c0`
- `OLEAUT32!__imp_VariantClear` at `0x18002b260`

## string_xrefs

- `0x18002b13e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x18002b1b8`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x18002b0d0`: ` xmlns:ps="http://schemas.microsoft.com/Passport/SoapServices/PPCRL"`
- `0x18002b10a`: `CKeyCache::ProcessKeyXml`
- `0x18002b1a0`: `hr = ::CreateDOM(CA2WEX<>(strKeyPurposesXml, CP_UTF8), cvNamespaces, pXMLDoc)`
- `0x18002b1f6`: `hr = pXMLDoc->selectSingleNode(c_bstrKeyPurposes, &pPurposesNode)`
- `0x18002b22a`: `hr = ProcessKeyXml(pExecutionContext, pPurposesNode)`

## pseudocode

```c

```

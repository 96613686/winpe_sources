# WdcSaveXmlDocument(IXMLDOMDocument *,ushort const *)

- ea: `0x18002a7dc`
- end: `0x18002aa23`
- name: `?WdcSaveXmlDocument@@YAJPEAUIXMLDOMDocument@@PEBG@Z`
- size: `583`
- prototype: `int(struct IXMLDOMDocument *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18002cd58`
- `0x180052168`

## callees

- `0x18000b854`
- `0x18002a7dc`
- `0x180067730`
- `0x180086010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002a83e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a943`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a83e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002a943`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a829`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a8c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a9ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a829`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a8c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002a9ee`
- `OLEAUT32!__imp_VariantInit` at `0x18002a81a`
- `OLEAUT32!__imp_VariantInit` at `0x18002a81a`
- `OLEAUT32!__imp_VariantClear` at `0x18002a932`
- `OLEAUT32!__imp_VariantClear` at `0x18002a9df`
- `OLEAUT32!__imp_VariantClear` at `0x18002a932`
- `OLEAUT32!__imp_VariantClear` at `0x18002a9df`

## string_xrefs

- `0x18002a837`: `<?xml version='1.0' encoding='UTF-8'?>\n<xsl:stylesheet version='1.0'  xmlns:xsl='http://www.w3.org/1999/XSL/Transform'>\n<xsl:output method='xml' version='1.0'  encoding='UTF-8' indent='yes'/>\n<xsl:template match='@* | node()'>\n  <xsl:copy>\n    <xsl:apply-templates select='@* | node()'/>\n  </xsl:copy>\n</xsl:template>\n</xsl:stylesheet>`
- `0x18002a9c8`: `WdcSaveXmlDocument`

## pseudocode

```c

```

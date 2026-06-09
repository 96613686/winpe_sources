# CSaxContentHandler::characters(wchar_t const *,int)

- ea: `0x18000eac0`
- end: `0x18000eaeb`
- name: `?characters@CSaxContentHandler@@UEAAJPEB_WH@Z`
- size: `43`
- prototype: `__int64 __fastcall(CSaxContentHandler *this, const wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180008a10`

## string_xrefs

- `0x18000eac9`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\saxcontenthandler.cpp"`
- `0x18000ead8`: `[XmlFilter SAX Content Handler] CSaxContentHandler::characters(): Chars:%.*s`

## pseudocode

```c
__int64 __fastcall CSaxContentHandler::characters(CSaxContentHandler *this, const wchar_t *a2, unsigned int a3)
{
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\saxcontenthandler.cpp\"",
    (const wchar_t *)0x139,
    (unsigned int)L"[XmlFilter SAX Content Handler] CSaxContentHandler::characters(): Chars:%.*s",
    (const wchar_t *)a3,
    a2);
  return 0;
}

```

## disassembly

```asm
0x18000eac0  sub     rsp, 38h
0x18000eac4  mov     [rsp+38h+var_18], rdx
0x18000eac9  lea     rcx, aOnecoreuapBase_5; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000ead0  mov     r9d, r8d; wchar_t *
0x18000ead3  mov     edx, 139h; wchar_t *
0x18000ead8  lea     r8, aXmlfilterSaxCo_5; "[XmlFilter SAX Content Handler] CSaxCon"...
0x18000eadf  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x18000eae4  xor     eax, eax
0x18000eae6  add     rsp, 38h
0x18000eaea  retn
```

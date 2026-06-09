# CSaxContentHandler::endPrefixMapping(wchar_t const *,int)

- ea: `0x18000eb90`
- end: `0x18000ebbb`
- name: `?endPrefixMapping@CSaxContentHandler@@UEAAJPEB_WH@Z`
- size: `43`
- prototype: `__int64 __fastcall(CSaxContentHandler *this, const wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000e98c`

## string_xrefs

- `0x18000eb99`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\saxcontenthandler.cpp"`
- `0x18000eba8`: `[XmlFilter SAX Content Handler] CSaxContentHandler::endPrefixMapping(): Prefix:%.*s`

## pseudocode

```c
__int64 __fastcall CSaxContentHandler::endPrefixMapping(CSaxContentHandler *this, const wchar_t *a2, unsigned int a3)
{
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\saxcontenthandler.cpp\"",
    (const wchar_t *)0x17B,
    (unsigned int)L"[XmlFilter SAX Content Handler] CSaxContentHandler::endPrefixMapping(): Prefix:%.*s",
    (const wchar_t *)a3,
    a2);
  return 0;
}

```

## disassembly

```asm
0x18000eb90  sub     rsp, 38h
0x18000eb94  mov     [rsp+38h+var_18], rdx
0x18000eb99  lea     rcx, aOnecoreuapBase_5; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000eba0  mov     r9d, r8d; wchar_t *
0x18000eba3  mov     edx, 17Bh; wchar_t *
0x18000eba8  lea     r8, aXmlfilterSaxCo_7; "[XmlFilter SAX Content Handler] CSaxCon"...
0x18000ebaf  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000ebb4  xor     eax, eax
0x18000ebb6  add     rsp, 38h
0x18000ebba  retn
```

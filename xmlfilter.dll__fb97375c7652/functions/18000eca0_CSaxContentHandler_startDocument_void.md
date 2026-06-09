# CSaxContentHandler::startDocument(void)

- ea: `0x18000eca0`
- end: `0x18000ecc3`
- name: `?startDocument@CSaxContentHandler@@UEAAJXZ`
- size: `35`
- prototype: `__int64 __fastcall(CSaxContentHandler *this, __int64, __int64, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000e98c`

## string_xrefs

- `0x18000ecb0`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\saxcontenthandler.cpp"`
- `0x18000eca4`: `[XmlFilter SAX Content Handler] CSaxContentHandler::startDocument():`

## pseudocode

```c
__int64 __fastcall CSaxContentHandler::startDocument(
        CSaxContentHandler *this,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4)
{
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\saxcontenthandler.cpp\"",
    (const wchar_t *)0x8D,
    (unsigned int)L"[XmlFilter SAX Content Handler] CSaxContentHandler::startDocument():",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18000eca0  sub     rsp, 28h
0x18000eca4  lea     r8, aXmlfilterSaxCo_4; "[XmlFilter SAX Content Handler] CSaxCon"...
0x18000ecab  mov     edx, 8Dh; wchar_t *
0x18000ecb0  lea     rcx, aOnecoreuapBase_5; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000ecb7  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000ecbc  xor     eax, eax
0x18000ecbe  add     rsp, 28h
0x18000ecc2  retn
```

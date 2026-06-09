# CSaxContentHandler::endDocument(void)

- ea: `0x18000eb00`
- end: `0x18000eb23`
- name: `?endDocument@CSaxContentHandler@@UEAAJXZ`
- size: `35`
- prototype: `__int64 __fastcall(CSaxContentHandler *this, __int64, __int64, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000e98c`

## string_xrefs

- `0x18000eb10`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\saxcontenthandler.cpp"`
- `0x18000eb04`: `[XmlFilter SAX Content Handler] CSaxContentHandler::endDocument():`

## pseudocode

```c
__int64 __fastcall CSaxContentHandler::endDocument(CSaxContentHandler *this, __int64 a2, __int64 a3, const wchar_t *a4)
{
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\saxcontenthandler.cpp\"",
    (const wchar_t *)0xA7,
    (unsigned int)L"[XmlFilter SAX Content Handler] CSaxContentHandler::endDocument():",
    a4);
  return 0;
}

```

## disassembly

```asm
0x18000eb00  sub     rsp, 28h
0x18000eb04  lea     r8, aXmlfilterSaxCo_6; "[XmlFilter SAX Content Handler] CSaxCon"...
0x18000eb0b  mov     edx, 0A7h; wchar_t *
0x18000eb10  lea     rcx, aOnecoreuapBase_5; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000eb17  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000eb1c  xor     eax, eax
0x18000eb1e  add     rsp, 28h
0x18000eb22  retn
```

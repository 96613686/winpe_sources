# CSaxContentHandler::skippedEntity(wchar_t const *,int)

- ea: `0x18000ec60`
- end: `0x18000ec8b`
- name: `?skippedEntity@CSaxContentHandler@@UEAAJPEB_WH@Z`
- size: `43`
- prototype: `__int64 __fastcall(CSaxContentHandler *this, const wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180008a10`

## string_xrefs

- `0x18000ec69`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\saxcontenthandler.cpp"`
- `0x18000ec78`: `[XmlFilter SAX Content Handler] CSaxContentHandler::skippedEntity(): Name:%.*s`

## pseudocode

```c
__int64 __fastcall CSaxContentHandler::skippedEntity(CSaxContentHandler *this, const wchar_t *a2, unsigned int a3)
{
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\saxcontenthandler.cpp\"",
    (const wchar_t *)0x1D9,
    (const wchar_t *)L"[XmlFilter SAX Content Handler] CSaxContentHandler::skippedEntity(): Name:%.*s",
    (const wchar_t *)a3,
    a2);
  return 0;
}

```

## disassembly

```asm
0x18000ec60  sub     rsp, 38h
0x18000ec64  mov     [rsp+38h+var_18], rdx
0x18000ec69  lea     rcx, aOnecoreuapBase_5; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000ec70  mov     r9d, r8d; wchar_t *
0x18000ec73  mov     edx, 1D9h; wchar_t *
0x18000ec78  lea     r8, aXmlfilterSaxCo_1; "[XmlFilter SAX Content Handler] CSaxCon"...
0x18000ec7f  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x18000ec84  xor     eax, eax
0x18000ec86  add     rsp, 38h
0x18000ec8a  retn
```

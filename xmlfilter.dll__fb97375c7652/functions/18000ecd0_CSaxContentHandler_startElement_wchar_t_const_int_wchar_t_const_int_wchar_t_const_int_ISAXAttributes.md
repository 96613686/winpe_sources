# CSaxContentHandler::startElement(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,ISAXAttributes *)

- ea: `0x18000ecd0`
- end: `0x18000ed2a`
- name: `?startElement@CSaxContentHandler@@UEAAJPEB_WH0H0HPEAUISAXAttributes@@@Z`
- size: `90`
- prototype: `__int64 __fastcall(CSaxContentHandler *this, const wchar_t *, unsigned int, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000e98c`
- `0x18000ecd0`

## string_xrefs

- `0x18000ed10`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\saxcontenthandler.cpp"`
- `0x18000ed04`: `[XmlFilter SAX Content Handler] CSaxContentHandler::startElement():NamespaceUri:%.*s LocalName:%.*s pwchQName:%.*s`

## pseudocode

```c
__int64 __fastcall CSaxContentHandler::startElement(
        CSaxContentHandler *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        int a5,
        const wchar_t *a6,
        int a7)
{
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\saxcontenthandler.cpp\"",
    (const wchar_t *)0xE2,
    (unsigned int)L"[XmlFilter SAX Content Handler] CSaxContentHandler::startElement():NamespaceUri:%.*s LocalName:%.*s pwchQName:%.*s",
    (const wchar_t *)a3,
    a2,
    a5,
    a4,
    a7,
    a6);
  return 0;
}

```

## disassembly

```asm
0x18000ecd0  sub     rsp, 68h
0x18000ecd4  mov     rax, [rsp+68h+arg_28]
0x18000ecdc  mov     [rsp+68h+var_28], rax
0x18000ece1  mov     eax, [rsp+68h+arg_30]
0x18000ece8  mov     [rsp+68h+var_30], eax
0x18000ecec  mov     [rsp+68h+var_38], r9
0x18000ecf1  mov     eax, [rsp+68h+arg_20]
0x18000ecf8  mov     [rsp+68h+var_40], eax
0x18000ecfc  mov     [rsp+68h+var_48], rdx
0x18000ed01  mov     r9d, r8d; wchar_t *
0x18000ed04  lea     r8, aXmlfilterSaxCo_0; "[XmlFilter SAX Content Handler] CSaxCon"...
0x18000ed0b  mov     edx, 0E2h; wchar_t *
0x18000ed10  lea     rcx, aOnecoreuapBase_5; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000ed17  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000ed1c  xor     eax, eax
0x18000ed1e  jmp     short loc_18000ED24
0x18000ed20  mov     eax, [rsp+68h+var_18]
0x18000ed24  add     rsp, 68h
0x18000ed28  retn
```

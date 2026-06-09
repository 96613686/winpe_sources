# CSaxContentHandler::startPrefixMapping(wchar_t const *,int,wchar_t const *,int)

- ea: `0x18000ed30`
- end: `0x18000ed68`
- name: `?startPrefixMapping@CSaxContentHandler@@UEAAJPEB_WH0H@Z`
- size: `56`
- prototype: `__int64 __fastcall(CSaxContentHandler *this, const wchar_t *, unsigned int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000e98c`

## string_xrefs

- `0x18000ed38`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\saxcontenthandler.cpp"`
- `0x18000ed4b`: `[XmlFilter SAX Content Handler] CSaxContentHandler::startPrefixMapping(): Prefix:%.*s Uri:%.*s`

## pseudocode

```c
__int64 __fastcall CSaxContentHandler::startPrefixMapping(
        CSaxContentHandler *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        int a5)
{
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\saxcontenthandler.cpp\"",
    (const wchar_t *)0x15F,
    (unsigned int)L"[XmlFilter SAX Content Handler] CSaxContentHandler::startPrefixMapping(): Prefix:%.*s Uri:%.*s",
    (const wchar_t *)a3,
    a2,
    a5,
    a4);
  return 0;
}

```

## disassembly

```asm
0x18000ed30  sub     rsp, 48h
0x18000ed34  mov     eax, [rsp+48h+arg_20]
0x18000ed38  lea     rcx, aOnecoreuapBase_5; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000ed3f  mov     [rsp+48h+var_18], r9
0x18000ed44  mov     r9d, r8d; wchar_t *
0x18000ed47  mov     [rsp+48h+var_20], eax
0x18000ed4b  lea     r8, aXmlfilterSaxCo_3; "[XmlFilter SAX Content Handler] CSaxCon"...
0x18000ed52  mov     [rsp+48h+var_28], rdx
0x18000ed57  mov     edx, 15Fh; wchar_t *
0x18000ed5c  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000ed61  xor     eax, eax
0x18000ed63  add     rsp, 48h
0x18000ed67  retn
```

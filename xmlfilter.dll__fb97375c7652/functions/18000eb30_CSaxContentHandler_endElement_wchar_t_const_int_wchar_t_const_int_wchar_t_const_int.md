# CSaxContentHandler::endElement(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)

- ea: `0x18000eb30`
- end: `0x18000eb8a`
- name: `?endElement@CSaxContentHandler@@UEAAJPEB_WH0H0H@Z`
- size: `90`
- prototype: `__int64 __fastcall(CSaxContentHandler *this, const wchar_t *, unsigned int, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000e98c`
- `0x18000eb30`

## string_xrefs

- `0x18000eb70`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\saxcontenthandler.cpp"`
- `0x18000eb64`: `[XmlFilter SAX Content Handler] CSaxContentHandler::endElement():NamespaceUri:%.*s LocalName:%.*s pwchQName:%.*s`

## pseudocode

```c
__int64 __fastcall CSaxContentHandler::endElement(
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
    (const wchar_t *)0x117,
    (unsigned int)L"[XmlFilter SAX Content Handler] CSaxContentHandler::endElement():NamespaceUri:%.*s LocalName:%.*s pwchQName:%.*s",
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
0x18000eb30  sub     rsp, 68h
0x18000eb34  mov     rax, [rsp+68h+arg_28]
0x18000eb3c  mov     [rsp+68h+var_28], rax
0x18000eb41  mov     eax, [rsp+68h+arg_30]
0x18000eb48  mov     [rsp+68h+var_30], eax
0x18000eb4c  mov     [rsp+68h+var_38], r9
0x18000eb51  mov     eax, [rsp+68h+arg_20]
0x18000eb58  mov     [rsp+68h+var_40], eax
0x18000eb5c  mov     [rsp+68h+var_48], rdx
0x18000eb61  mov     r9d, r8d; wchar_t *
0x18000eb64  lea     r8, aXmlfilterSaxCo_2; "[XmlFilter SAX Content Handler] CSaxCon"...
0x18000eb6b  mov     edx, 117h; wchar_t *
0x18000eb70  lea     rcx, aOnecoreuapBase_5; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000eb77  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000eb7c  xor     eax, eax
0x18000eb7e  jmp     short loc_18000EB84
0x18000eb80  mov     eax, [rsp+68h+var_18]
0x18000eb84  add     rsp, 68h
0x18000eb88  retn
```

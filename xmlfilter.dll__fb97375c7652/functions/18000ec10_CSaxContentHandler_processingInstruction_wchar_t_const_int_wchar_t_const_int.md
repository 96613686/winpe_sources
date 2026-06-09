# CSaxContentHandler::processingInstruction(wchar_t const *,int,wchar_t const *,int)

- ea: `0x18000ec10`
- end: `0x18000ec48`
- name: `?processingInstruction@CSaxContentHandler@@UEAAJPEB_WH0H@Z`
- size: `56`
- prototype: `__int64 __fastcall(CSaxContentHandler *this, const wchar_t *, unsigned int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180008a10`

## string_xrefs

- `0x18000ec18`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\saxcontenthandler.cpp"`
- `0x18000ec2b`: `[XmlFilter SAX Content Handler] CSaxContentHandler::processingInstruction(): Target:%.*s Data:%.*s`

## pseudocode

```c
__int64 __fastcall CSaxContentHandler::processingInstruction(
        CSaxContentHandler *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        int a5)
{
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\saxcontenthandler.cpp\"",
    (const wchar_t *)0x1BD,
    (const wchar_t *)L"[XmlFilter SAX Content Handler] CSaxContentHandler::processingInstruction(): Target:%.*s Data:%.*s",
    (const wchar_t *)a3,
    a2,
    a5,
    a4);
  return 0;
}

```

## disassembly

```asm
0x18000ec10  sub     rsp, 48h
0x18000ec14  mov     eax, [rsp+48h+arg_20]
0x18000ec18  lea     rcx, aOnecoreuapBase_5; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000ec1f  mov     [rsp+48h+var_18], r9
0x18000ec24  mov     r9d, r8d; wchar_t *
0x18000ec27  mov     [rsp+48h+var_20], eax
0x18000ec2b  lea     r8, aXmlfilterSaxCo; "[XmlFilter SAX Content Handler] CSaxCon"...
0x18000ec32  mov     [rsp+48h+var_28], rdx
0x18000ec37  mov     edx, 1BDh; wchar_t *
0x18000ec3c  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x18000ec41  xor     eax, eax
0x18000ec43  add     rsp, 48h
0x18000ec47  retn
```

# CFilterImpContentHandler::endDocument(void)

- ea: `0x18000f5f0`
- end: `0x18000f637`
- name: `?endDocument@CFilterImpContentHandler@@UEAAJXZ`
- size: `71`
- prototype: `__int64 __fastcall(CFilterImpContentHandler *this, __int64, __int64, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18000e98c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f61c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f629`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f61c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f629`

## string_xrefs

- `0x18000f600`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\filterimpcontenthandler.cpp"`
- `0x18000f5f9`: `[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::endDocument():`

## pseudocode

```c
__int64 __fastcall CFilterImpContentHandler::endDocument(
        CFilterImpContentHandler *this,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4)
{
  void *v5; // rcx

  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\filterimpcontenthandler.cpp\"",
    (const wchar_t *)0x127,
    (unsigned int)L"[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::endDocument():",
    a4);
  v5 = (void *)*((_QWORD *)this + 52);
  *((_BYTE *)this + 40) = 1;
  SetEvent(v5);
  SetEvent(*((HANDLE *)this + 51));
  return 0;
}

```

## disassembly

```asm
0x18000f5f0  push    rbx
0x18000f5f2  sub     rsp, 20h
0x18000f5f6  mov     rbx, rcx
0x18000f5f9  lea     r8, aXmlfilterIfilt_1; "[XmlFilter IFilter implementation Conte"...
0x18000f600  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000f607  mov     edx, 127h; wchar_t *
0x18000f60c  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000f611  mov     rcx, [rbx+1A0h]; hEvent
0x18000f618  mov     byte ptr [rbx+28h], 1
0x18000f61c  call    cs:__imp_SetEvent
0x18000f622  mov     rcx, [rbx+198h]; hEvent
0x18000f629  call    cs:__imp_SetEvent
0x18000f62f  xor     eax, eax
0x18000f631  add     rsp, 20h
0x18000f635  pop     rbx
0x18000f636  retn
```

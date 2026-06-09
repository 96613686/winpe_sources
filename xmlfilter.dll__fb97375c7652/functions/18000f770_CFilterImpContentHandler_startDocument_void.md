# CFilterImpContentHandler::startDocument(void)

- ea: `0x18000f770`
- end: `0x18000f7d4`
- name: `?startDocument@CFilterImpContentHandler@@UEAAJXZ`
- size: `100`
- prototype: `__int64 __fastcall(CFilterImpContentHandler *this, __int64, __int64, const wchar_t *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18000b724`
- `0x18000e98c`
- `0x18000f770`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f79c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f79c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f7ac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f7ac`

## string_xrefs

- `0x18000f7bb`: `onecoreuap\base\appmodel\search\filters\xml\FilterImpContentHandler.h`
- `0x18000f780`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\filterimpcontenthandler.cpp"`
- `0x18000f779`: `[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::startDocument():`

## pseudocode

```c
__int64 __fastcall CFilterImpContentHandler::startDocument(
        CFilterImpContentHandler *this,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4)
{
  void *v5; // rcx
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\filterimpcontenthandler.cpp\"",
    (const wchar_t *)0x108,
    (unsigned int)L"[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::startDocument():",
    a4);
  v5 = (void *)*((_QWORD *)this + 51);
  *((_BYTE *)this + 41) = 1;
  SetEvent(v5);
  if ( WaitForSingleObject(*((HANDLE *)this + 52), 0xFFFFFFFF) )
    wil::details::in1diag3::Return_GetLastError(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\xml\\FilterImpContentHandler.h",
      v6);
  return 0;
}

```

## disassembly

```asm
0x18000f770  push    rbx
0x18000f772  sub     rsp, 20h
0x18000f776  mov     rbx, rcx
0x18000f779  lea     r8, aXmlfilterIfilt_6; "[XmlFilter IFilter implementation Conte"...
0x18000f780  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000f787  mov     edx, 108h; wchar_t *
0x18000f78c  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000f791  mov     rcx, [rbx+198h]; hEvent
0x18000f798  mov     byte ptr [rbx+29h], 1
0x18000f79c  call    cs:__imp_SetEvent
0x18000f7a2  mov     rcx, [rbx+1A0h]; hHandle
0x18000f7a9  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f7ac  call    cs:__imp_WaitForSingleObject
0x18000f7b2  test    eax, eax
0x18000f7b4  jz      short loc_18000F7CC
0x18000f7b6  mov     rcx, [rsp+28h]; this
0x18000f7bb  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000f7c2  mov     edx, 54h ; 'T'; void *
0x18000f7c7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f7cc  xor     eax, eax
0x18000f7ce  add     rsp, 20h
0x18000f7d2  pop     rbx
0x18000f7d3  retn
```

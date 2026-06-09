# CFilterImpContentHandler::characters(wchar_t const *,int)

- ea: `0x18000f540`
- end: `0x18000f5e2`
- name: `?characters@CFilterImpContentHandler@@UEAAJPEB_WH@Z`
- size: `162`
- prototype: `__int64 __fastcall(HANDLE *this, wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x180008a10`
- `0x18000b724`
- `0x18000ed94`
- `0x18000f358`
- `0x18000f540`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f5a5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f5a5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f5b5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f5b5`

## string_xrefs

- `0x18000f5c4`: `onecoreuap\base\appmodel\search\filters\xml\FilterImpContentHandler.h`
- `0x18000f56d`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\filterimpcontenthandler.cpp"`
- `0x18000f561`: `[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::characters():Chars:%.*s`

## pseudocode

```c
__int64 __fastcall CFilterImpContentHandler::characters(HANDLE *this, wchar_t *a2, unsigned int a3)
{
  CFilterImpContentHandler *v5; // rcx
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  wchar_t *v9; // [rsp+48h] [rbp+10h] BYREF
  int v10; // [rsp+50h] [rbp+18h] BYREF

  v10 = a3;
  v9 = a2;
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\filterimpcontenthandler.cpp\"",
    (const wchar_t *)0x2A6,
    (unsigned int)L"[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::characters():Chars:%.*s",
    (const wchar_t *)a3,
    a2);
  if ( a3 )
  {
    CFilterImpContentHandler::RemoveWhiteSpace(v5, (const wchar_t **)&v9, &v10);
    CFilterImpContentHandler::AddContentToBuffer((CFilterImpContentHandler *)this, v9, v10);
    SetEvent(this[51]);
    if ( WaitForSingleObject(this[52], 0xFFFFFFFF) )
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0x54,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\xml\\FilterImpContentHandler.h",
        v6);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f540  mov     rax, rsp
0x18000f543  mov     [rax+8], rbx
0x18000f547  mov     [rax+18h], r8d
0x18000f54b  mov     [rax+10h], rdx
0x18000f54f  push    rdi
0x18000f550  sub     rsp, 30h
0x18000f554  mov     ebx, r8d
0x18000f557  mov     [rax-18h], rdx
0x18000f55b  mov     rdi, rcx
0x18000f55e  mov     r9d, r8d; wchar_t *
0x18000f561  lea     r8, aXmlfilterIfilt_5; "[XmlFilter IFilter implementation Conte"...
0x18000f568  mov     edx, 2A6h; wchar_t *
0x18000f56d  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000f574  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x18000f579  test    ebx, ebx
0x18000f57b  jz      short loc_18000F5D5
0x18000f57d  lea     r8, [rsp+38h+arg_10]; int *
0x18000f582  lea     rdx, [rsp+38h+arg_8]; wchar_t **
0x18000f587  call    ?RemoveWhiteSpace@CFilterImpContentHandler@@IEAAXAEAPEB_WAEAH@Z; CFilterImpContentHandler::RemoveWhiteSpace(wchar_t const * &,int &)
0x18000f58c  mov     r8d, [rsp+38h+arg_10]; int
0x18000f591  mov     rcx, rdi; this
0x18000f594  mov     rdx, [rsp+38h+arg_8]; wchar_t *
0x18000f599  call    ?AddContentToBuffer@CFilterImpContentHandler@@IEAAXPEB_WH@Z; CFilterImpContentHandler::AddContentToBuffer(wchar_t const *,int)
0x18000f59e  mov     rcx, [rdi+198h]; hEvent
0x18000f5a5  call    cs:__imp_SetEvent
0x18000f5ab  mov     rcx, [rdi+1A0h]; hHandle
0x18000f5b2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f5b5  call    cs:__imp_WaitForSingleObject
0x18000f5bb  test    eax, eax
0x18000f5bd  jz      short loc_18000F5D5
0x18000f5bf  mov     rcx, [rsp+38h]; this
0x18000f5c4  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000f5cb  mov     edx, 54h ; 'T'; void *
0x18000f5d0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f5d5  mov     rbx, [rsp+38h+arg_0]
0x18000f5da  xor     eax, eax
0x18000f5dc  add     rsp, 30h
0x18000f5e0  pop     rdi
0x18000f5e1  retn
```

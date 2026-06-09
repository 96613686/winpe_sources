# CFilterImpContentHandler::endElement(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int)

- ea: `0x18000f640`
- end: `0x18000f767`
- name: `?endElement@CFilterImpContentHandler@@UEAAJPEB_WH0H0H@Z`
- size: `295`
- prototype: `__int64 __fastcall(CFilterImpContentHandler *this, const wchar_t *, unsigned int, const wchar_t *, int, const wchar_t *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000b724`
- `0x18000e98c`
- `0x18000ed94`
- `0x18000f41c`
- `0x18000f640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f709`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000f709`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f719`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f719`

## string_xrefs

- `0x18000f728`: `onecoreuap\base\appmodel\search\filters\xml\FilterImpContentHandler.h`
- `0x18000f68c`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\filterimpcontenthandler.cpp"`
- `0x18000f680`: `[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::endElement():NamespaceUri:%.*s LocalName:%.*s pwchQName:%.*s`

## pseudocode

```c
__int64 __fastcall CFilterImpContentHandler::endElement(
        CFilterImpContentHandler *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        int a5,
        const wchar_t *a6,
        int a7)
{
  _QWORD *v8; // rbx
  unsigned int v9; // esi
  unsigned int v10; // esi
  const char *v11; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\filterimpcontenthandler.cpp\"",
    (const wchar_t *)0x1DE,
    (unsigned int)L"[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::endElement():NamespaceUri"
                   ":%.*s LocalName:%.*s pwchQName:%.*s",
    (const wchar_t *)a3,
    a2,
    a5,
    a4,
    a7,
    a6);
  v8 = (_QWORD *)((char *)this + 120);
  --*((_DWORD *)this + 100);
  try
  {
    CVarVector<CElement,64>::SetSize((char *)this + 120, *((unsigned int *)this + 100));
    v9 = *((_DWORD *)this + 100);
    if ( v9 )
    {
      if ( *((_DWORD *)this + 98) < v9 )
        CVarVector<CElement,64>::SetSize((char *)this + 120, v9);
      if ( *(_DWORD *)(*v8 + 4LL * (v9 - 1)) != *((_DWORD *)this + 9) )
      {
        v10 = *((_DWORD *)this + 100);
        if ( *((_DWORD *)this + 98) < v10 )
          CVarVector<CElement,64>::SetSize((char *)this + 120, v10);
        *((_DWORD *)this + 9) = *(_DWORD *)(*v8 + 4LL * (v10 - 1));
        SetEvent(*((HANDLE *)this + 51));
        if ( WaitForSingleObject(*((HANDLE *)this + 52), 0xFFFFFFFF) )
          wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x54,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\xml\\FilterImpContentHandler.h",
            v11);
      }
      CFilterImpContentHandler::AddContentToBuffer(this, L" ", 1);
    }
    result = 0;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      497,
      "onecoreuap\\base\\appmodel\\search\\filters\\xml\\filterimpcontenthandler.cpp");
  }
  return result;
}

```

## disassembly

```asm
0x18000f640  mov     r11, rsp
0x18000f643  mov     [r11+10h], rbx
0x18000f647  mov     [r11+18h], rsi
0x18000f64b  push    rdi
0x18000f64c  sub     rsp, 50h
0x18000f650  mov     rdi, rcx
0x18000f653  mov     rax, [rsp+58h+arg_28]
0x18000f65b  mov     [r11-18h], rax
0x18000f65f  mov     eax, [rsp+58h+arg_30]
0x18000f666  mov     [rsp+58h+var_20], eax
0x18000f66a  mov     [r11-28h], r9
0x18000f66e  mov     eax, [rsp+58h+arg_20]
0x18000f675  mov     [rsp+58h+var_30], eax
0x18000f679  mov     [r11-38h], rdx
0x18000f67d  mov     r9d, r8d; wchar_t *
0x18000f680  lea     r8, aXmlfilterIfilt_0; "[XmlFilter IFilter implementation Conte"...
0x18000f687  mov     edx, 1DEh; wchar_t *
0x18000f68c  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000f693  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000f698  lea     rbx, [rdi+78h]
0x18000f69c  dec     dword ptr [rbx+118h]
0x18000f6a2  mov     edx, [rbx+118h]
0x18000f6a8  mov     rcx, rbx
0x18000f6ab  call    ?SetSize@?$CVarVector@VCElement@@$0EA@@@QEAAXK@Z; CVarVector<CElement,64>::SetSize(ulong)
0x18000f6b0  mov     esi, [rdi+190h]
0x18000f6b6  test    esi, esi
0x18000f6b8  jz      loc_18000F74E
0x18000f6be  cmp     [rbx+110h], esi
0x18000f6c4  jnb     short loc_18000F6D0
0x18000f6c6  mov     edx, esi
0x18000f6c8  mov     rcx, rbx
0x18000f6cb  call    ?SetSize@?$CVarVector@VCElement@@$0EA@@@QEAAXK@Z; CVarVector<CElement,64>::SetSize(ulong)
0x18000f6d0  lea     edx, [rsi-1]
0x18000f6d3  mov     rcx, [rbx]
0x18000f6d6  mov     eax, [rdi+24h]
0x18000f6d9  cmp     [rcx+rdx*4], eax
0x18000f6dc  jz      short loc_18000F739
0x18000f6de  mov     esi, [rbx+118h]
0x18000f6e4  cmp     [rbx+110h], esi
0x18000f6ea  jnb     short loc_18000F6F6
0x18000f6ec  mov     edx, esi
0x18000f6ee  mov     rcx, rbx
0x18000f6f1  call    ?SetSize@?$CVarVector@VCElement@@$0EA@@@QEAAXK@Z; CVarVector<CElement,64>::SetSize(ulong)
0x18000f6f6  lea     ecx, [rsi-1]
0x18000f6f9  mov     rax, [rbx]
0x18000f6fc  mov     ecx, [rax+rcx*4]
0x18000f6ff  mov     [rdi+24h], ecx
0x18000f702  mov     rcx, [rdi+198h]; hEvent
0x18000f709  call    cs:__imp_SetEvent
0x18000f70f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000f712  mov     rcx, [rdi+1A0h]; hHandle
0x18000f719  call    cs:__imp_WaitForSingleObject
0x18000f71f  test    eax, eax
0x18000f721  jz      short loc_18000F739
0x18000f723  mov     rcx, [rsp+58h]; this
0x18000f728  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000f72f  mov     edx, 54h ; 'T'; void *
0x18000f734  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f739  mov     r8d, 1; int
0x18000f73f  lea     rdx, asc_18001B6D4; " "
0x18000f746  mov     rcx, rdi; this
0x18000f749  call    ?AddContentToBuffer@CFilterImpContentHandler@@IEAAXPEB_WH@Z; CFilterImpContentHandler::AddContentToBuffer(wchar_t const *,int)
0x18000f74e  xor     eax, eax
0x18000f750  jmp     short loc_18000F756
0x18000f752  mov     eax, [rsp+58h+arg_0]
0x18000f756  mov     rbx, [rsp+58h+arg_8]
0x18000f75b  mov     rsi, [rsp+58h+arg_10]
0x18000f760  add     rsp, 50h
0x18000f764  pop     rdi
0x18000f765  retn
```

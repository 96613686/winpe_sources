# CXmlContentFilter::FinalConstruct(void)

- ea: `0x1800060c0`
- end: `0x180006152`
- name: `?FinalConstruct@CXmlContentFilter@@QEAAJXZ`
- size: `146`
- prototype: `__int64 __fastcall(CXmlContentFilter *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011574`
- `0x1800116b0`

## callees

- `0x180005f70`
- `0x1800060c0`
- `0x180008c60`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006106`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006106`

## string_xrefs

- `0x180006126`: `[XmlFilter XML Content Filter] IPersistFile::Load:Could not create XML DOM document object`
- `0x180006132`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp"`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::FinalConstruct(CXmlContentFilter *this)
{
  LPVOID *ppv; // rdi
  __int64 v3; // rcx
  HRESULT Instance; // edi
  const wchar_t *v5; // r9
  __int64 result; // rax
  void *retaddr; // [rsp+38h] [rbp+0h]

  try
  {
    ppv = (LPVOID *)((char *)this + 80);
    v3 = *((_QWORD *)this + 10);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *ppv = 0;
    Instance = CoCreateInstance(
                 &GUID_88d96a0c_f192_11d4_a65f_0040963251e5,
                 0,
                 1u,
                 &GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802,
                 ppv);
    if ( Instance < 0 )
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\xmlcontentfilter.cpp\"",
        (const wchar_t *)0x4A,
        (unsigned int)L"[XmlFilter XML Content Filter] IPersistFile::Load:Could not create XML DOM document object",
        v5);
    }
    else
    {
      Instance = CFilterImpContentHandler::InitParsingReadingEvents((CXmlContentFilter *)((char *)this + 88));
      *((_BYTE *)this + 520) = 0;
    }
    result = (unsigned int)Instance;
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      81,
      "onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp");
  }
  return result;
}

```

## disassembly

```asm
0x1800060c0  mov     [rsp+arg_8], rbx
0x1800060c5  push    rdi
0x1800060c6  sub     rsp, 30h
0x1800060ca  mov     rbx, rcx
0x1800060cd  lea     rdi, [rcx+50h]
0x1800060d1  mov     rcx, [rdi]
0x1800060d4  test    rcx, rcx
0x1800060d7  jz      short loc_1800060E6
0x1800060d9  mov     rax, [rcx]
0x1800060dc  mov     rax, [rax+10h]
0x1800060e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060e5  nop
0x1800060e6  mov     qword ptr [rdi], 0
0x1800060ed  mov     [rsp+38h+ppv], rdi; ppv
0x1800060f2  lea     r9, _GUID_a4f96ed0_f829_476e_81c0_cdc7bd2a0802; riid
0x1800060f9  xor     edx, edx; pUnkOuter
0x1800060fb  lea     r8d, [rdx+1]; dwClsContext
0x1800060ff  lea     rcx, _GUID_88d96a0c_f192_11d4_a65f_0040963251e5; rclsid
0x180006106  call    cs:__imp_CoCreateInstance
0x18000610c  mov     edi, eax
0x18000610e  test    eax, eax
0x180006110  js      short loc_180006126
0x180006112  lea     rcx, [rbx+58h]; this
0x180006116  call    ?InitParsingReadingEvents@CFilterImpContentHandler@@QEAAJXZ; CFilterImpContentHandler::InitParsingReadingEvents(void)
0x18000611b  mov     edi, eax
0x18000611d  mov     byte ptr [rbx+208h], 0
0x180006124  jmp     short loc_18000613E
0x180006126  lea     r8, aXmlfilterXmlCo_0; "[XmlFilter XML Content Filter] IPersist"...
0x18000612d  mov     edx, 4Ah ; 'J'; wchar_t *
0x180006132  lea     rcx, aOnecoreuapBase_0; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180006139  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000613e  mov     eax, edi
0x180006140  jmp     short loc_180006146
0x180006142  mov     eax, [rsp+38h+arg_0]
0x180006146  mov     rbx, [rsp+38h+arg_8]
0x18000614b  add     rsp, 30h
0x18000614f  pop     rdi
0x180006150  retn
```

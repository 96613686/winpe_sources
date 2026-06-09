# CXmlContentFilter::Init(ulong,ulong,tagFULLPROPSPEC const *,ulong *)

- ea: `0x180008b40`
- end: `0x180008c57`
- name: `?Init@CXmlContentFilter@@UEAAJKKPEBUtagFULLPROPSPEC@@PEAK@Z`
- size: `279`
- prototype: `__int64 __fastcall(_QWORD *Context, __int64, int, const wchar_t *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005f70`
- `0x180008b40`
- `0x18000b724`
- `0x1800140d0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180008bfe`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180008bfe`

## string_xrefs

- `0x180008b63`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp"`
- `0x180008bd2`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp"`
- `0x180008c1c`: `onecoreuap\base\appmodel\search\filters\xml\xmlcontentfilter.cpp`
- `0x180008b57`: `[XmlFilter XML Content Filter] IFilter::Init(): Returnable properties specification is invalid`
- `0x180008bc6`: `[XmlFilter XML Content Filter] CXmlContentFilter::FinalConstruct(): Could set the content handler`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::Init(_QWORD *Context, __int64 a2, int a3, const wchar_t *a4, unsigned int *a5)
{
  __int64 result; // rax
  char *v7; // rdi
  __int64 v8; // rcx
  int v9; // edi
  const wchar_t *v10; // r9
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a3 )
  {
    if ( !a4 )
      goto LABEL_3;
  }
  else if ( a4 )
  {
LABEL_3:
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\xmlcontentfilter.cpp\"",
      (const wchar_t *)0x14C,
      (unsigned int)L"[XmlFilter XML Content Filter] IFilter::Init(): Returnable properties specification is invalid",
      a4);
    return 2147942487LL;
  }
  v7 = (char *)(Context + 11);
  try
  {
    (*(void (**)(void))(Context[11] + 112LL))();
    *((_DWORD *)Context + 31) = 0;
    v8 = Context[10];
    if ( !v8 )
      _com_issue_error(0);
    v9 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v8 + 80LL))(v8, v7);
    if ( v9 >= 0 )
    {
      (*(void (__fastcall **)(_QWORD *))(*Context + 8LL))(Context);
      if ( QueueUserWorkItem((LPTHREAD_START_ROUTINE)CXmlContentFilter::GetParsedAsyncHelper, Context, 0) )
      {
        if ( a5 )
          *a5 = 0;
        *((_BYTE *)Context + 520) = 1;
        result = 0;
      }
      else
      {
        (*(void (__fastcall **)(_QWORD *))(*Context + 16LL))(Context);
        result = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0x16E,
                   (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp",
                   v11);
      }
    }
    else
    {
      SearchIndexerTrace::Error(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\xmlcontentfilter.cpp\"",
        (const wchar_t *)0x162,
        (unsigned int)L"[XmlFilter XML Content Filter] CXmlContentFilter::FinalConstruct(): Could set the content handler",
        v10);
      result = (unsigned int)v9;
    }
  }
  catch ( ... )
  {
    indexer::result::details::result_from_caught_exception<1>(
      retaddr,
      383,
      "onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp");
  }
  return result;
}

```

## disassembly

```asm
0x180008b40  mov     [rsp+arg_0], rbx
0x180008b45  push    rdi
0x180008b46  sub     rsp, 20h
0x180008b4a  mov     rbx, rcx
0x180008b4d  test    r8d, r8d
0x180008b50  jnz     short loc_180008B85
0x180008b52  test    r9, r9
0x180008b55  jz      short loc_180008B8A
0x180008b57  lea     r8, aXmlfilterXmlCo_8; "[XmlFilter XML Content Filter] IFilter:"...
0x180008b5e  mov     edx, 14Ch; wchar_t *
0x180008b63  lea     rcx, aOnecoreuapBase_0; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180008b6a  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180008b6f  mov     eax, 80070057h
0x180008b74  jmp     short loc_180008B7A
0x180008b76  mov     eax, [rsp+28h+arg_10]
0x180008b7a  mov     rbx, [rsp+28h+arg_0]
0x180008b7f  add     rsp, 20h
0x180008b83  pop     rdi
0x180008b84  retn
0x180008b85  test    r9, r9
0x180008b88  jz      short loc_180008B57
0x180008b8a  lea     rdi, [rcx+58h]
0x180008b8e  mov     rax, [rdi]
0x180008b91  mov     rcx, rdi
0x180008b94  mov     rax, [rax+70h]
0x180008b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b9d  mov     dword ptr [rbx+7Ch], 0
0x180008ba4  mov     rcx, [rbx+50h]; int
0x180008ba8  test    rcx, rcx
0x180008bab  jz      loc_180008C50
0x180008bb1  mov     rax, [rcx]
0x180008bb4  mov     rdx, rdi
0x180008bb7  mov     rax, [rax+50h]
0x180008bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bc0  mov     edi, eax
0x180008bc2  test    eax, eax
0x180008bc4  jns     short loc_180008BE2
0x180008bc6  lea     r8, aXmlfilterXmlCo_2; "[XmlFilter XML Content Filter] CXmlCont"...
0x180008bcd  mov     edx, 162h; wchar_t *
0x180008bd2  lea     rcx, aOnecoreuapBase_0; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180008bd9  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180008bde  mov     eax, edi
0x180008be0  jmp     short loc_180008B7A
0x180008be2  mov     rax, [rbx]
0x180008be5  mov     rcx, rbx
0x180008be8  mov     rax, [rax+8]
0x180008bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bf1  xor     r8d, r8d; Flags
0x180008bf4  mov     rdx, rbx; Context
0x180008bf7  lea     rcx, ?GetParsedAsyncHelper@CXmlContentFilter@@SAKPEAX@Z; Function
0x180008bfe  call    cs:__imp_QueueUserWorkItem
0x180008c04  test    eax, eax
0x180008c06  jnz     short loc_180008C32
0x180008c08  mov     rax, [rbx]
0x180008c0b  mov     rcx, rbx
0x180008c0e  mov     rax, [rax+10h]
0x180008c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c17  mov     rcx, [rsp+28h]; this
0x180008c1c  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\fil"...
0x180008c23  mov     edx, 16Eh; void *
0x180008c28  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008c2d  jmp     loc_180008B7A
0x180008c32  mov     rax, [rsp+28h+arg_20]
0x180008c37  test    rax, rax
0x180008c3a  jz      short loc_180008C42
0x180008c3c  mov     dword ptr [rax], 0
0x180008c42  mov     byte ptr [rbx+208h], 1
0x180008c49  xor     eax, eax
0x180008c4b  jmp     loc_180008B7A
0x180008c50  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```

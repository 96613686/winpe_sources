# CXmlContentFilter::GetValue(tagPROPVARIANT * *)

- ea: `0x1800086b0`
- end: `0x1800086ed`
- name: `?GetValue@CXmlContentFilter@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `61`
- prototype: `__int64 __fastcall(CXmlContentFilter *this, struct tagPROPVARIANT **, __int64, const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180005f70`
- `0x1800086b0`

## string_xrefs

- `0x1800086d0`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp"`
- `0x1800086c4`: `[XmlFilter XML Content Filter] CXmlContentFilter::GetValue(): Call failed`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::GetValue(
        CXmlContentFilter *this,
        struct tagPROPVARIANT **a2,
        __int64 a3,
        const wchar_t *a4)
{
  if ( !*((_BYTE *)this + 520) )
    return 2147751696LL;
  SearchIndexerTrace::Error(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\xmlcontentfilter.cpp\"",
    (const wchar_t *)0x20C,
    (unsigned int)L"[XmlFilter XML Content Filter] CXmlContentFilter::GetValue(): Call failed",
    a4);
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800086b0  sub     rsp, 28h
0x1800086b4  cmp     byte ptr [rcx+208h], 0
0x1800086bb  jnz     short loc_1800086C4
0x1800086bd  mov     eax, 80041710h
0x1800086c2  jmp     short loc_1800086E7
0x1800086c4  lea     r8, aXmlfilterXmlCo_1; "[XmlFilter XML Content Filter] CXmlCont"...
0x1800086cb  mov     edx, 20Ch; wchar_t *
0x1800086d0  lea     rcx, aOnecoreuapBase_0; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800086d7  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800086dc  mov     eax, 8000FFFFh
0x1800086e1  jmp     short loc_1800086E7
0x1800086e3  mov     eax, [rsp+28h+arg_0]
0x1800086e7  add     rsp, 28h
0x1800086eb  retn
```

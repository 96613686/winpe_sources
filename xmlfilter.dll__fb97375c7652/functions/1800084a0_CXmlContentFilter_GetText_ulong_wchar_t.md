# CXmlContentFilter::GetText(ulong *,wchar_t *)

- ea: `0x1800084a0`
- end: `0x180008500`
- name: `?GetText@CXmlContentFilter@@UEAAJPEAKPEA_W@Z`
- size: `96`
- prototype: `__int64 __fastcall(CXmlContentFilter *__hidden this, unsigned int *, wchar_t *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x180005f70`
- `0x1800084a0`
- `0x18000f13c`

## string_xrefs

- `0x1800084e1`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp"`
- `0x1800084d5`: `[XmlFilter XML Content Filter] CXmlContentFilter::GetText(): Call failed`

## pseudocode

```c
__int64 __fastcall CXmlContentFilter::GetText(CXmlContentFilter *this, unsigned int *a2, wchar_t *a3)
{
  unsigned int Text; // ebx
  const wchar_t *v5; // r9

  if ( !*((_BYTE *)this + 520) )
    return 2147751696LL;
  Text = CFilterImpContentHandler::GetText((CXmlContentFilter *)((char *)this + 88), a2, a3);
  if ( (int)(Text + 0x80000000) < 0 || Text == -2147215615 )
    return Text;
  SearchIndexerTrace::Error(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\xmlcontentfilter.cpp\"",
    (const wchar_t *)0x1E4,
    (unsigned int)L"[XmlFilter XML Content Filter] CXmlContentFilter::GetText(): Call failed",
    v5);
  return Text;
}

```

## disassembly

```asm
0x1800084a0  push    rbx
0x1800084a2  sub     rsp, 20h
0x1800084a6  cmp     byte ptr [rcx+208h], 0
0x1800084ad  jnz     short loc_1800084B6
0x1800084af  mov     eax, 80041710h
0x1800084b4  jmp     short loc_1800084F9
0x1800084b6  add     rcx, 58h ; 'X'; this
0x1800084ba  call    ?GetText@CFilterImpContentHandler@@QEAAJPEAKPEA_W@Z; CFilterImpContentHandler::GetText(ulong *,wchar_t *)
0x1800084bf  mov     ebx, eax
0x1800084c1  mov     eax, 80000000h
0x1800084c6  lea     ecx, [rbx+rax]
0x1800084c9  test    eax, ecx
0x1800084cb  jnz     short loc_1800084F1
0x1800084cd  cmp     ebx, 80041701h
0x1800084d3  jz      short loc_1800084F1
0x1800084d5  lea     r8, aXmlfilterXmlCo_7; "[XmlFilter XML Content Filter] CXmlCont"...
0x1800084dc  mov     edx, 1E4h; wchar_t *
0x1800084e1  lea     rcx, aOnecoreuapBase_0; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800084e8  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800084ed  mov     eax, ebx
0x1800084ef  jmp     short loc_1800084F9
0x1800084f1  mov     eax, ebx
0x1800084f3  jmp     short loc_1800084F9
0x1800084f5  mov     eax, [rsp+28h+arg_0]
0x1800084f9  add     rsp, 20h
0x1800084fd  pop     rbx
0x1800084fe  retn
```

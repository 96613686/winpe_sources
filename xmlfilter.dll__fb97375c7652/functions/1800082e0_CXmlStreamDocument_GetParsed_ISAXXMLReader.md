# CXmlStreamDocument::GetParsed(ISAXXMLReader *)

- ea: `0x1800082e0`
- end: `0x180008405`
- name: `?GetParsed@CXmlStreamDocument@@UEAAJPEAUISAXXMLReader@@@Z`
- size: `293`
- prototype: `__int64 __fastcall(CXmlStreamDocument *__hidden this, struct ISAXXMLReader *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005f70`
- `0x1800082e0`
- `0x18000cb28`
- `0x1800140d0`
- `0x180017010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800083e2`
- `OLEAUT32!__imp_VariantClear` at `0x1800083f2`
- `OLEAUT32!__imp_VariantClear` at `0x1800083e2`
- `OLEAUT32!__imp_VariantClear` at `0x1800083f2`

## string_xrefs

- `0x18000833a`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp"`
- `0x1800083d0`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\xmlcontentfilter.cpp"`
- `0x18000832e`: `[XmlFilter XML Content Filter] CXmlStreamDocument::GetParsed(): Could not seek to beginning of stream`
- `0x1800083c4`: `[XmlFilter XML Content Filter] CXmlStreamDocument:GetParsed() Could not parse %s`

## pseudocode

```c
__int64 __fastcall CXmlStreamDocument::GetParsed(CXmlStreamDocument *this, struct ISAXXMLReader *a2)
{
  __int64 v4; // rcx
  int v5; // edi
  const wchar_t *v6; // r9
  LONGLONG v8; // rcx
  const wchar_t *v9; // rax
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF
  VARIANTARG v11; // [rsp+50h] [rbp-28h] BYREF

  v4 = *((_QWORD *)this + 9);
  if ( !v4 )
    _com_issue_error(0);
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v4 + 40LL))(v4, 0, 0, 0);
  if ( v5 < 0 )
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\xmlcontentfilter.cpp\"",
      (const wchar_t *)0x91,
      (unsigned int)L"[XmlFilter XML Content Filter] CXmlStreamDocument::GetParsed(): Could not seek to beginning of stream",
      v6);
    return (unsigned int)v5;
  }
  v8 = *((_QWORD *)this + 9);
  pvarg.vt = 13;
  pvarg.llVal = v8;
  if ( v8 )
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v8 + 8LL))(v8);
  v11 = pvarg;
  v5 = ((__int64 (__fastcall *)(struct ISAXXMLReader *, VARIANTARG *))a2->lpVtbl->parse)(a2, &v11);
  if ( v5 < 0 )
  {
    v9 = (const wchar_t *)(*(__int64 (__fastcall **)(CXmlStreamDocument *))(*(_QWORD *)this + 16LL))(this);
    SearchIndexerTrace::Warning(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\xmlcontentfilter.cpp\"",
      (const wchar_t *)0x9D,
      (unsigned int)L"[XmlFilter XML Content Filter] CXmlStreamDocument:GetParsed() Could not parse %s",
      v9);
    VariantClear(&pvarg);
    return (unsigned int)v5;
  }
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x1800082e0  mov     [rsp+arg_8], rbx
0x1800082e5  mov     [rsp+arg_10], rsi
0x1800082ea  push    rdi
0x1800082eb  sub     rsp, 70h
0x1800082ef  mov     rsi, rdx
0x1800082f2  mov     rbx, rcx
0x1800082f5  mov     [rsp+78h+arg_0], 0
0x180008301  mov     rcx, [rcx+48h]; int
0x180008305  test    rcx, rcx
0x180008308  jz      loc_1800083FF
0x18000830e  mov     rax, [rcx]
0x180008311  xor     r9d, r9d
0x180008314  xor     r8d, r8d
0x180008317  mov     rdx, [rsp+78h+arg_0]
0x18000831f  mov     rax, [rax+28h]
0x180008323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008328  mov     edi, eax
0x18000832a  test    eax, eax
0x18000832c  jns     short loc_18000835A
0x18000832e  lea     r8, aXmlfilterXmlCo_9; "[XmlFilter XML Content Filter] CXmlStre"...
0x180008335  mov     edx, 91h; wchar_t *
0x18000833a  lea     rcx, aOnecoreuapBase_0; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180008341  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180008346  mov     eax, edi
0x180008348  lea     r11, [rsp+78h+var_8]
0x18000834d  mov     rbx, [r11+18h]
0x180008351  mov     rsi, [r11+20h]
0x180008355  mov     rsp, r11
0x180008358  pop     rdi
0x180008359  retn
0x18000835a  mov     rcx, [rbx+48h]
0x18000835e  mov     eax, 0Dh
0x180008363  mov     word ptr [rsp+78h+pvarg], ax
0x180008368  mov     qword ptr [rsp+78h+pvarg+8], rcx
0x18000836d  test    rcx, rcx
0x180008370  jz      short loc_18000837F
0x180008372  mov     rax, [rcx]
0x180008375  mov     rax, [rax+8]
0x180008379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000837e  nop
0x18000837f  movups  xmm0, xmmword ptr [rsp+78h+pvarg]
0x180008384  movaps  [rsp+78h+var_28], xmm0
0x180008389  movsd   xmm1, qword ptr [rsp+78h+pvarg+10h]
0x18000838f  movsd   [rsp+78h+var_18], xmm1
0x180008395  mov     rax, [rsi]
0x180008398  lea     rdx, [rsp+78h+var_28]
0x18000839d  mov     rcx, rsi
0x1800083a0  mov     rax, [rax+98h]
0x1800083a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083ac  mov     edi, eax
0x1800083ae  test    eax, eax
0x1800083b0  jns     short loc_1800083ED
0x1800083b2  mov     rcx, [rbx]
0x1800083b5  mov     rax, [rcx+10h]
0x1800083b9  mov     rcx, rbx
0x1800083bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083c1  mov     r9, rax; wchar_t *
0x1800083c4  lea     r8, aXmlfilterXmlCo_6; "[XmlFilter XML Content Filter] CXmlStre"...
0x1800083cb  mov     edx, 9Dh; wchar_t *
0x1800083d0  lea     rcx, aOnecoreuapBase_0; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800083d7  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x1800083dc  nop
0x1800083dd  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1800083e2  call    cs:__imp_VariantClear
0x1800083e8  jmp     loc_180008346
0x1800083ed  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1800083f2  call    cs:__imp_VariantClear
0x1800083f8  xor     eax, eax
0x1800083fa  jmp     loc_180008348
0x1800083ff  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```

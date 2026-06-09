# WcmCommon::Xml::Document::AddSelectionNamespace(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180029048`
- end: `0x18002935a`
- name: `?AddSelectionNamespace@Document@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z`
- size: `786`
- prototype: `void __fastcall(struct IUnknown ***, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023974`

## callees

- `0x180002590`
- `0x18000fe0c`
- `0x180022394`
- `0x180028804`
- `0x180028c8c`
- `0x180028e74`
- `0x180028ef8`
- `0x180029048`
- `0x1800299dc`
- `0x180029a5c`
- `0x18003127c`
- `0x180031290`
- `0x180031604`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800292ab`
- `OLEAUT32!__imp_SysAllocString` at `0x1800292ab`
- `OLEAUT32!__imp_VariantInit` at `0x1800290ad`
- `OLEAUT32!__imp_VariantInit` at `0x180029125`
- `OLEAUT32!__imp_VariantInit` at `0x1800290ad`
- `OLEAUT32!__imp_VariantInit` at `0x180029125`
- `OLEAUT32!__imp_VariantClear` at `0x18002915a`
- `OLEAUT32!__imp_VariantClear` at `0x180029165`
- `OLEAUT32!__imp_VariantClear` at `0x1800292e7`
- `OLEAUT32!__imp_VariantClear` at `0x18002915a`
- `OLEAUT32!__imp_VariantClear` at `0x180029165`
- `OLEAUT32!__imp_VariantClear` at `0x1800292e7`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002913a`
- `OLEAUT32!__imp_VariantChangeType` at `0x18002913a`

## string_xrefs

- `0x180029185`: ` xmlns`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall WcmCommon::Xml::Document::AddSelectionNamespace(struct IUnknown ***a1, _QWORD *a2, _QWORD *a3)
{
  struct IUnknown *v6; // rbx
  _bstr_t *v7; // rdi
  _QWORD *v8; // rdx
  int v9; // eax
  HRESULT v10; // eax
  __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdi
  OLECHAR **v15; // rbx
  unsigned __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdi
  OLECHAR **v19; // rbx
  struct IUnknown *v20; // rdi
  const OLECHAR *v21; // rbx
  _bstr_t *v22; // rax
  _bstr_t *v23; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v24[8]; // [rsp+38h] [rbp-41h] BYREF
  VARIANTARG pvarSrc; // [rsp+40h] [rbp-39h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-19h] BYREF
  OLECHAR *psz[2]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v28; // [rsp+88h] [rbp+Fh]
  unsigned __int64 v29; // [rsp+90h] [rbp+17h]

  v6 = **a1;
  if ( !v6 )
    _com_issue_error(-2147467261);
  v7 = _bstr_t::_bstr_t((_bstr_t *)v24, L"SelectionNamespaces");
  v23 = v7;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v8 = *(_QWORD **)v7;
  if ( *(_QWORD *)v7 )
    v8 = (_QWORD *)*v8;
  v9 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD *, VARIANTARG *))v6->lpVtbl[27].QueryInterface)(
         v6,
         v8,
         &pvarg);
  if ( v9 < 0 )
    _com_issue_errorex(v9, v6, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60);
  pvarSrc = pvarg;
  pvarg.vt = 0;
  _bstr_t::~_bstr_t(v7);
  v23 = 0;
  if ( pvarSrc.vt == 8 )
  {
    _bstr_t::operator=(&v23, pvarSrc.llVal);
  }
  else
  {
    VariantInit(&pvarg);
    v10 = VariantChangeType(&pvarg, &pvarSrc, 0, 8u);
    if ( v10 < 0 )
      _com_issue_error(v10);
    _bstr_t::operator=(&v23, pvarg.llVal);
    VariantClear(&pvarg);
  }
  VariantClear(&pvarSrc);
  if ( v23 )
    v11 = *(_QWORD *)v23;
  else
    v11 = 0;
  std::wstring::wstring(psz, v11);
  std::wstring::append(psz, L" xmlns");
  if ( a2[2] )
  {
    std::wstring::append(psz, L":");
    v12 = a2[2];
    if ( a2[3] > 7u )
      a2 = (_QWORD *)*a2;
    v13 = v28;
    if ( v12 > v29 - v28 )
    {
      ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
        psz,
        v12);
    }
    else
    {
      v14 = v12 + v28;
      v28 += v12;
      v15 = psz;
      if ( v29 > 7 )
        v15 = (OLECHAR **)psz[0];
      memmove_0((char *)v15 + 2 * v13, a2, 2 * v12);
      *((_WORD *)v15 + v14) = 0;
    }
  }
  std::wstring::append(psz, L"='");
  v16 = a3[2];
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  v17 = v28;
  if ( v16 > v29 - v28 )
  {
    ____Reallocate_grow_by_V_lambda_1___1_____Append_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG_K___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Append_G_01_AEAAAEAV01_QEBG0_Z_PEBG_K_Z(
      psz,
      v16);
  }
  else
  {
    v18 = v16 + v28;
    v28 += v16;
    v19 = psz;
    if ( v29 > 7 )
      v19 = (OLECHAR **)psz[0];
    memmove_0((char *)v19 + 2 * v17, a3, 2 * v16);
    *((_WORD *)v19 + v18) = 0;
  }
  std::wstring::append(psz, L"'");
  v20 = **a1;
  if ( !v20 )
    _com_issue_error(-2147467261);
  v21 = (const OLECHAR *)psz;
  if ( v29 > 7 )
    v21 = psz[0];
  pvarSrc.vt = 8;
  pvarSrc.llVal = (LONGLONG)SysAllocString(v21);
  if ( !pvarSrc.llVal && v21 )
    _com_issue_error(-2147024882);
  v22 = _bstr_t::_bstr_t((_bstr_t *)v24, L"SelectionNamespaces");
  MSXML2::IXMLDOMDocument2::setProperty(v20, v22, &pvarSrc);
  VariantClear(&pvarSrc);
  std::wstring::~wstring((char **)psz);
  _bstr_t::~_bstr_t((_bstr_t *)&v23);
}

```

## disassembly

```asm
0x180029048  push    rbp
0x18002904a  push    rbx
0x18002904b  push    rsi
0x18002904c  push    rdi
0x18002904d  push    r13
0x18002904f  push    r14
0x180029051  push    r15
0x180029053  lea     rbp, [rsp-27h]
0x180029058  sub     rsp, 0A0h
0x18002905f  mov     rax, cs:__security_cookie
0x180029066  xor     rax, rsp
0x180029069  mov     [rbp+57h+var_38], rax
0x18002906d  mov     r14, r8
0x180029070  mov     rsi, rdx
0x180029073  mov     r15, rcx
0x180029076  mov     rax, [rcx]
0x180029079  mov     rbx, [rax]
0x18002907c  test    rbx, rbx
0x18002907f  jz      loc_18002932A
0x180029085  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18002908c  lea     rcx, [rbp+57h+var_98]; this
0x180029090  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180029095  mov     rdi, rax
0x180029098  mov     [rbp+57h+var_A0], rax
0x18002909c  xorps   xmm0, xmm0
0x18002909f  xor     eax, eax
0x1800290a1  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800290a5  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800290a9  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800290ad  call    cs:__imp_VariantInit
0x1800290b3  mov     rcx, [rbx]
0x1800290b6  mov     rax, [rcx+288h]
0x1800290bd  mov     rdx, [rdi]
0x1800290c0  test    rdx, rdx
0x1800290c3  jz      short loc_1800290C8
0x1800290c5  mov     rdx, [rdx]
0x1800290c8  lea     r8, [rbp+57h+pvarg]
0x1800290cc  mov     rcx, rbx
0x1800290cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290d4  test    eax, eax
0x1800290d6  js      loc_180029335
0x1800290dc  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x1800290e0  movups  xmmword ptr [rbp+57h+pvarSrc], xmm0
0x1800290e4  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x1800290e9  movsd   qword ptr [rbp+57h+pvarSrc+10h], xmm1
0x1800290ee  xor     eax, eax
0x1800290f0  mov     word ptr [rbp+57h+pvarg], ax
0x1800290f4  mov     rcx, rdi; this
0x1800290f7  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800290fc  nop
0x1800290fd  mov     [rbp+57h+var_A0], 0
0x180029105  mov     r13d, 8
0x18002910b  cmp     word ptr [rbp+57h+pvarSrc], r13w
0x180029110  jnz     short loc_180029121
0x180029112  mov     rdx, qword ptr [rbp+57h+pvarSrc+8]
0x180029116  lea     rcx, [rbp+57h+var_A0]
0x18002911a  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18002911f  jmp     short loc_180029161
0x180029121  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180029125  call    cs:__imp_VariantInit
0x18002912b  nop
0x18002912c  mov     r9d, r13d; vt
0x18002912f  xor     r8d, r8d; wFlags
0x180029132  lea     rdx, [rbp+57h+pvarSrc]; pvarSrc
0x180029136  lea     rcx, [rbp+57h+pvarg]; pvargDest
0x18002913a  call    cs:__imp_VariantChangeType
0x180029140  test    eax, eax
0x180029142  js      loc_180029347
0x180029148  mov     rdx, qword ptr [rbp+57h+pvarg+8]
0x18002914c  lea     rcx, [rbp+57h+var_A0]
0x180029150  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180029155  nop
0x180029156  lea     rcx, [rbp+57h+pvarg]; pvarg
0x18002915a  call    cs:__imp_VariantClear
0x180029160  nop
0x180029161  lea     rcx, [rbp+57h+pvarSrc]; pvarg
0x180029165  call    cs:__imp_VariantClear
0x18002916b  mov     rax, [rbp+57h+var_A0]
0x18002916f  test    rax, rax
0x180029172  jz      short loc_180029179
0x180029174  mov     rdx, [rax]
0x180029177  jmp     short loc_18002917B
0x180029179  xor     edx, edx
0x18002917b  lea     rcx, [rbp+57h+psz]
0x18002917f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029184  nop
0x180029185  lea     rdx, aXmlns; " xmlns"
0x18002918c  lea     rcx, [rbp+57h+psz]; Src
0x180029190  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180029195  cmp     qword ptr [rsi+10h], 0
0x18002919a  jz      short loc_180029209
0x18002919c  lea     rdx, asc_180037A88; ":"
0x1800291a3  lea     rcx, [rbp+57h+psz]; Src
0x1800291a7  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800291ac  mov     rdx, [rsi+10h]
0x1800291b0  cmp     qword ptr [rsi+18h], 7
0x1800291b5  jbe     short loc_1800291BA
0x1800291b7  mov     rsi, [rsi]
0x1800291ba  mov     rcx, [rbp+57h+var_48]
0x1800291be  mov     rax, [rbp+57h+var_40]
0x1800291c2  sub     rax, rcx
0x1800291c5  cmp     rdx, rax
0x1800291c8  ja      short loc_1800291F8
0x1800291ca  lea     rdi, [rdx+rcx]
0x1800291ce  mov     [rbp+57h+var_48], rdi
0x1800291d2  lea     rbx, [rbp+57h+psz]
0x1800291d6  cmp     [rbp+57h+var_40], 7
0x1800291db  cmova   rbx, [rbp+57h+psz]
0x1800291e0  lea     r8, [rdx+rdx]; Size
0x1800291e4  lea     rcx, [rbx+rcx*2]; void *
0x1800291e8  mov     rdx, rsi; Src
0x1800291eb  call    memmove_0
0x1800291f0  xor     eax, eax
0x1800291f2  mov     [rbx+rdi*2], ax
0x1800291f6  jmp     short loc_180029209
0x1800291f8  mov     [rsp+0D0h+var_B0], rdx; __int64
0x1800291fd  mov     r9, rsi
0x180029200  lea     rcx, [rbp+57h+psz]; Src
0x180029204  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x180029209  lea     rdx, asc_180037BB8; "='"
0x180029210  lea     rcx, [rbp+57h+psz]; Src
0x180029214  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180029219  mov     rdx, [r14+10h]
0x18002921d  cmp     qword ptr [r14+18h], 7
0x180029222  jbe     short loc_180029227
0x180029224  mov     r14, [r14]
0x180029227  mov     rcx, [rbp+57h+var_48]
0x18002922b  mov     rax, [rbp+57h+var_40]
0x18002922f  sub     rax, rcx
0x180029232  cmp     rdx, rax
0x180029235  ja      short loc_180029265
0x180029237  lea     rdi, [rdx+rcx]
0x18002923b  mov     [rbp+57h+var_48], rdi
0x18002923f  lea     rbx, [rbp+57h+psz]
0x180029243  cmp     [rbp+57h+var_40], 7
0x180029248  cmova   rbx, [rbp+57h+psz]
0x18002924d  lea     r8, [rdx+rdx]; Size
0x180029251  lea     rcx, [rbx+rcx*2]; void *
0x180029255  mov     rdx, r14; Src
0x180029258  call    memmove_0
0x18002925d  xor     eax, eax
0x18002925f  mov     [rbx+rdi*2], ax
0x180029263  jmp     short loc_180029276
0x180029265  mov     [rsp+0D0h+var_B0], rdx; __int64
0x18002926a  mov     r9, r14
0x18002926d  lea     rcx, [rbp+57h+psz]; Src
0x180029271  call    ??$_Reallocate_grow_by@V_lambda_1_@?1???$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Append@G@01@AEAAAEAV01@QEBG0@Z@PEBG_K@Z; std::wstring::_Reallocate_grow_by<`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64>(unsigned __int64,`std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *,unsigned __int64)
0x180029276  lea     rdx, asc_180037BC0; "'"
0x18002927d  lea     rcx, [rbp+57h+psz]; Src
0x180029281  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180029286  mov     rax, [r15]
0x180029289  mov     rdi, [rax]
0x18002928c  test    rdi, rdi
0x18002928f  jz      loc_18002931F
0x180029295  lea     rbx, [rbp+57h+psz]
0x180029299  cmp     [rbp+57h+var_40], 7
0x18002929e  cmova   rbx, [rbp+57h+psz]
0x1800292a3  mov     word ptr [rbp+57h+pvarSrc], r13w
0x1800292a8  mov     rcx, rbx; psz
0x1800292ab  call    cs:__imp_SysAllocString
0x1800292b1  mov     qword ptr [rbp+57h+pvarSrc+8], rax
0x1800292b5  test    rax, rax
0x1800292b8  jnz     short loc_1800292C3
0x1800292ba  test    rbx, rbx
0x1800292bd  jnz     loc_18002934F
0x1800292c3  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x1800292ca  lea     rcx, [rbp+57h+var_98]; this
0x1800292ce  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800292d3  lea     r8, [rbp+57h+pvarSrc]
0x1800292d7  mov     rdx, rax
0x1800292da  mov     rcx, rdi
0x1800292dd  call    ?setProperty@IXMLDOMDocument2@MSXML2@@QEAAJV_bstr_t@@AEBV_variant_t@@@Z; MSXML2::IXMLDOMDocument2::setProperty(_bstr_t,_variant_t const &)
0x1800292e2  nop
0x1800292e3  lea     rcx, [rbp+57h+pvarSrc]; pvarg
0x1800292e7  call    cs:__imp_VariantClear
0x1800292ed  nop
0x1800292ee  lea     rcx, [rbp+57h+psz]
0x1800292f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800292f7  nop
0x1800292f8  lea     rcx, [rbp+57h+var_A0]; this
0x1800292fc  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180029301  mov     rcx, [rbp+57h+var_38]
0x180029305  xor     rcx, rsp; StackCookie
0x180029308  call    __security_check_cookie
0x18002930d  add     rsp, 0A0h
0x180029314  pop     r15
0x180029316  pop     r14
0x180029318  pop     r13
0x18002931a  pop     rdi
0x18002931b  pop     rsi
0x18002931c  pop     rbx
0x18002931d  pop     rbp
0x18002931e  retn
0x18002931f  mov     ecx, 80004003h; int
0x180029324  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002932a  mov     ecx, 80004003h; int
0x18002932f  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180029335  lea     r8, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x18002933c  mov     rdx, rbx; struct IUnknown *
0x18002933f  mov     ecx, eax; int
0x180029341  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x180029347  mov     ecx, eax; int
0x180029349  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002934f  mov     ecx, 8007000Eh; int
0x180029354  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```

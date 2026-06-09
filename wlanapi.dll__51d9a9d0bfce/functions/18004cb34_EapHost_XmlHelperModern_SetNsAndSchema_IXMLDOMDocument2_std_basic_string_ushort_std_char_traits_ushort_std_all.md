# EapHost::XmlHelperModern::SetNsAndSchema(IXMLDOMDocument2 *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x18004cb34`
- end: `0x18004ce9b`
- name: `?SetNsAndSchema@XmlHelperModern@EapHost@@YAXPEAUIXMLDOMDocument2@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@5@2@Z`
- size: `871`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004c95c`

## callees

- `0x180017434`
- `0x1800174b8`
- `0x180019a20`
- `0x180026898`
- `0x1800398dc`
- `0x18003a098`
- `0x18003a124`
- `0x18003a638`
- `0x18004a9bc`
- `0x18004b240`
- `0x18004b89c`
- `0x18004b8bc`
- `0x18004c6c0`
- `0x18004c7ac`
- `0x18004cb34`
- `0x18004d51c`
- `0x18004d568`
- `0x18004dc1c`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18004ccf7`
- `OLEAUT32!__imp_VariantInit` at `0x18004cdca`
- `OLEAUT32!__imp_VariantInit` at `0x18004cdd6`
- `OLEAUT32!__imp_VariantInit` at `0x18004ccf7`
- `OLEAUT32!__imp_VariantInit` at `0x18004cdca`
- `OLEAUT32!__imp_VariantInit` at `0x18004cdd6`
- `OLEAUT32!__imp_VariantClear` at `0x18004cd0c`
- `OLEAUT32!__imp_VariantClear` at `0x18004cd2b`
- `OLEAUT32!__imp_VariantClear` at `0x18004ce35`
- `OLEAUT32!__imp_VariantClear` at `0x18004ce57`
- `OLEAUT32!__imp_VariantClear` at `0x18004cd0c`
- `OLEAUT32!__imp_VariantClear` at `0x18004cd2b`
- `OLEAUT32!__imp_VariantClear` at `0x18004ce35`
- `OLEAUT32!__imp_VariantClear` at `0x18004ce57`

## string_xrefs

- `0x18004cba9`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x18004cdab`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall EapHost::XmlHelperModern::SetNsAndSchema(__int64 a1, _QWORD *a2, _QWORD *a3, _QWORD *a4)
{
  unsigned int v8; // eax
  __int64 v9; // rdx
  _QWORD *v10; // rdi
  _QWORD *v11; // rbx
  IRecordInfo *v12; // rsi
  _QWORD *v13; // rdx
  _QWORD *v14; // rcx
  _QWORD *v15; // rdx
  VARIANTARG *variant_bstr_nothrow; // rax
  __int128 v17; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  unsigned int v19; // r14d
  const char *v20; // rax
  unsigned int v21; // eax
  __int64 v23; // [rsp+38h] [rbp-D0h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C8h] BYREF
  IRecordInfo *v25; // [rsp+58h] [rbp-B0h]
  void *v26; // [rsp+60h] [rbp-A8h] BYREF
  IRecordInfo *v27; // [rsp+68h] [rbp-A0h] BYREF
  VARIANTARG v28; // [rsp+70h] [rbp-98h] BYREF
  IRecordInfo *v29; // [rsp+88h] [rbp-80h]
  void **v30; // [rsp+90h] [rbp-78h]
  char v31; // [rsp+98h] [rbp-70h]
  __int64 v32; // [rsp+9Ch] [rbp-6Ch]
  int v33; // [rsp+A8h] [rbp-60h]
  VARIANTARG v34; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD Src[3]; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int64 v36; // [rsp+F0h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  v31 = 0;
  v32 = 0;
  v30 = &EapHost::EapMethodType::`vftable';
  v33 = 0;
  if ( a3[1] - *a3 != a4[1] - *a4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
      (const char *)retaddr);
  wil::make_bstr(&v28, L"SelectionNamespaces");
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  wil::make_variant_bstr_nothrow(&pvarg.decVal.Lo32, a2);
  *(_OWORD *)&v34.vt = *(_OWORD *)&pvarg.decVal.Lo32;
  v34.pRecInfo = v25;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, VARIANTARG *))(*(_QWORD *)a1 + 640LL))(a1, *(_QWORD *)&v28.vt, &v34);
  if ( v8 )
    EapHost::XmlHelperModern::GetXmlErrorAndThrow((EapHost::XmlHelperModern *)v8);
  *(GUID *)&v34.vt = CLSID_XMLSchemaCache60;
  *(_QWORD *)&pvarg.vt = 0;
  LODWORD(v23) = 1;
  ___capture_UIXMLDOMSchemaCollection2__A6AHAEBUguid_winrt__PEAXI0PEAPEAX__EAEBU23_AEAPEAXAEAI_winrt__YA_AU__com_ptr_UIXMLDOMSchemaCollection2___0_A6AHAEBUguid_0_PEAXI0PEAPEAX__E0AEAPEAXAEAI_Z(
    &v27,
    v9,
    &v34,
    &pvarg,
    &v23);
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(&v26);
  v10 = (_QWORD *)*a3;
  v11 = (_QWORD *)*a4;
  v12 = v27;
  while ( v11 != (_QWORD *)a4[1] )
  {
    if ( v10[3] <= 7u )
      v13 = v10;
    else
      v13 = (_QWORD *)*v10;
    wil::make_bstr(&v23, v13);
    std::wstring::wstring(Src, v26);
    if ( v11[3] <= 7u )
      v14 = v11;
    else
      v14 = (_QWORD *)*v11;
    std::_WChar_traits<unsigned short>::length(v14);
    std::wstring::_Append<unsigned short>(Src);
    v15 = Src;
    if ( v36 > 7 )
      v15 = (_QWORD *)Src[0];
    variant_bstr_nothrow = (VARIANTARG *)wil::make_variant_bstr_nothrow(&v34, v15);
    if ( &pvarg.decVal.Lo32 != (ULONG *)variant_bstr_nothrow )
    {
      v17 = *(_OWORD *)&variant_bstr_nothrow->vt;
      pRecInfo = variant_bstr_nothrow->pRecInfo;
      VariantInit(variant_bstr_nothrow);
      wil::last_error_context::last_error_context((wil::last_error_context *)&pvarg);
      VariantClear((VARIANTARG *)&pvarg.decVal.8);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&pvarg);
      *(_OWORD *)&pvarg.decVal.Lo32 = v17;
      v25 = pRecInfo;
    }
    VariantClear(&v34);
    *(_OWORD *)&v34.vt = *(_OWORD *)&pvarg.decVal.Lo32;
    v34.pRecInfo = v25;
    v19 = ((__int64 (__fastcall *)(IRecordInfo *, __int64, VARIANTARG *))v12->lpVtbl->GetName)(v12, v23, &v34);
    if ( v19 )
    {
      v20 = (const char *)Src;
      if ( v36 > 7 )
        v20 = (const char *)Src[0];
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x57,
        (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
        (const char *)v19,
        (int)"Error adding schema '%ls'",
        v20);
      EapHost::XmlHelperModern::GetXmlErrorAndThrow((EapHost::XmlHelperModern *)v19);
    }
    std::wstring::~wstring(Src);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
    v11 += 4;
    v10 += 4;
  }
  VariantInit((VARIANTARG *)&v28.decVal.8);
  VariantInit((VARIANTARG *)&v28.decVal.8);
  v28.iVal = 13;
  v28.pRecInfo = v12;
  ((void (__fastcall *)(IRecordInfo *))v12->lpVtbl->AddRef)(v12);
  *(_OWORD *)&v34.vt = *(_OWORD *)&v28.decVal.Lo32;
  v34.pRecInfo = v29;
  v21 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)a1 + 624LL))(a1, &v34);
  if ( v21 )
    EapHost::XmlHelperModern::GetXmlErrorAndThrow((EapHost::XmlHelperModern *)v21);
  VariantClear((VARIANTARG *)&v28.decVal.8);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v26);
  winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v27);
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  return wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
}

```

## disassembly

```asm
0x18004cb34  mov     rax, rsp
0x18004cb37  mov     [rax+18h], rbx
0x18004cb3b  mov     [rax+20h], rsi
0x18004cb3f  push    rbp
0x18004cb40  push    rdi
0x18004cb41  push    r12
0x18004cb43  push    r14
0x18004cb45  push    r15
0x18004cb47  lea     rbp, [rax-48h]
0x18004cb4b  sub     rsp, 120h
0x18004cb52  movaps  xmmword ptr [rax-38h], xmm6
0x18004cb56  movaps  xmmword ptr [rax-48h], xmm7
0x18004cb5a  mov     rax, cs:__security_cookie
0x18004cb61  xor     rax, rsp
0x18004cb64  mov     [rbp+40h+var_50], rax
0x18004cb68  mov     r15, r9
0x18004cb6b  mov     rdi, r8
0x18004cb6e  mov     rbx, rdx
0x18004cb71  mov     r12, rcx
0x18004cb74  mov     [rbp+40h+var_B0], 0
0x18004cb78  mov     [rbp+40h+var_AC], 0
0x18004cb80  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18004cb87  mov     [rbp+40h+var_B8], rax
0x18004cb8b  mov     [rbp+40h+var_A0], 0
0x18004cb92  mov     r9, [rbp+48h]; char *
0x18004cb96  mov     rcx, [r8+8]
0x18004cb9a  sub     rcx, [r8]
0x18004cb9d  mov     rax, [r15+8]
0x18004cba1  sub     rax, [r15]
0x18004cba4  cmp     rcx, rax
0x18004cba7  jz      short loc_18004CBBE
0x18004cba9  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x18004cbb0  mov     edx, 3Ah ; ':'; void *
0x18004cbb5  mov     rcx, r9; this
0x18004cbb8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004cbbe  lea     rdx, aSelectionnames; "SelectionNamespaces"
0x18004cbc5  lea     rcx, [rsp+140h+var_D8]
0x18004cbca  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18004cbcf  nop
0x18004cbd0  cmp     qword ptr [rbx+18h], 7
0x18004cbd5  jbe     short loc_18004CBDA
0x18004cbd7  mov     rbx, [rbx]
0x18004cbda  mov     rdx, rbx
0x18004cbdd  lea     rcx, [rsp+140h+pvarg+8]
0x18004cbe2  call    ?make_variant_bstr_nothrow@wil@@YA?AV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@1@PEBG@Z; wil::make_variant_bstr_nothrow(ushort const *)
0x18004cbe7  nop
0x18004cbe8  movups  xmm0, xmmword ptr [rsp+140h+pvarg+8]
0x18004cbed  movsd   xmm1, [rsp+140h+var_F0]
0x18004cbf3  movaps  xmmword ptr [rbp+40h+var_90], xmm0
0x18004cbf7  movsd   qword ptr [rbp+40h+var_90+10h], xmm1
0x18004cbfc  mov     rax, [r12]
0x18004cc00  lea     r8, [rbp+40h+var_90]
0x18004cc04  mov     rdx, qword ptr [rsp+140h+var_D8]
0x18004cc09  mov     rcx, r12
0x18004cc0c  mov     rax, [rax+280h]
0x18004cc13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc18  test    eax, eax
0x18004cc1a  jz      short loc_18004CC24
0x18004cc1c  mov     ecx, eax; this
0x18004cc1e  call    ?GetXmlErrorAndThrow@XmlHelperModern@EapHost@@YAXJ@Z; EapHost::XmlHelperModern::GetXmlErrorAndThrow(long)
0x18004cc24  movups  xmm0, xmmword ptr cs:CLSID_XMLSchemaCache60.Data1
0x18004cc2b  movdqu  xmmword ptr [rbp+40h+var_90], xmm0
0x18004cc30  mov     qword ptr [rsp+140h+pvarg], 0
0x18004cc39  mov     dword ptr [rsp+140h+var_110], 1
0x18004cc41  lea     rax, [rsp+140h+var_110]
0x18004cc46  mov     qword ptr [rsp+140h+var_120], rax
0x18004cc4b  lea     r9, [rsp+140h+pvarg]
0x18004cc50  lea     r8, [rbp+40h+var_90]
0x18004cc54  lea     rcx, [rsp+140h+var_E0]
0x18004cc59  call    ??$capture@UIXMLDOMSchemaCollection2@@A6AHAEBUguid@winrt@@PEAXI0PEAPEAX@_EAEBU23@AEAPEAXAEAI@winrt@@YA?AU?$com_ptr@UIXMLDOMSchemaCollection2@@@0@A6AHAEBUguid@0@PEAXI0PEAPEAX@_E0AEAPEAXAEAI@Z
0x18004cc5e  nop
0x18004cc5f  lea     rcx, [rsp+140h+var_E8]
0x18004cc64  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x18004cc69  nop
0x18004cc6a  mov     rdi, [rdi]
0x18004cc6d  mov     rbx, [r15]
0x18004cc70  mov     rsi, [rsp+140h+var_E0]
0x18004cc75  cmp     rbx, [r15+8]
0x18004cc79  jz      loc_18004CDC5
0x18004cc7f  cmp     qword ptr [rdi+18h], 7
0x18004cc84  jbe     short loc_18004CC8B
0x18004cc86  mov     rdx, [rdi]
0x18004cc89  jmp     short loc_18004CC8E
0x18004cc8b  mov     rdx, rdi
0x18004cc8e  lea     rcx, [rsp+140h+var_110]
0x18004cc93  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18004cc98  nop
0x18004cc99  mov     rdx, [rsp+140h+var_E8]
0x18004cc9e  lea     rcx, [rbp+40h+Src]
0x18004cca2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004cca7  nop
0x18004cca8  cmp     qword ptr [rbx+18h], 7
0x18004ccad  jbe     short loc_18004CCB4
0x18004ccaf  mov     rcx, [rbx]
0x18004ccb2  jmp     short loc_18004CCB7
0x18004ccb4  mov     rcx, rbx
0x18004ccb7  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18004ccbc  mov     r8, rax
0x18004ccbf  mov     rdx, rcx
0x18004ccc2  lea     rcx, [rbp+40h+Src]; Src
0x18004ccc6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004cccb  lea     rdx, [rbp+40h+Src]
0x18004cccf  cmp     [rbp+40h+var_58], 7
0x18004ccd4  cmova   rdx, [rbp+40h+Src]
0x18004ccd9  lea     rcx, [rbp+40h+var_90]
0x18004ccdd  call    ?make_variant_bstr_nothrow@wil@@YA?AV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@1@PEBG@Z; wil::make_variant_bstr_nothrow(ushort const *)
0x18004cce2  lea     rcx, [rsp+140h+pvarg+8]
0x18004cce7  cmp     rcx, rax
0x18004ccea  jz      short loc_18004CD27
0x18004ccec  movups  xmm6, xmmword ptr [rax]
0x18004ccef  movsd   xmm7, qword ptr [rax+10h]
0x18004ccf4  mov     rcx, rax; pvarg
0x18004ccf7  call    cs:__imp_VariantInit
0x18004ccfd  lea     rcx, [rsp+140h+pvarg]; this
0x18004cd02  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004cd07  lea     rcx, [rsp+140h+pvarg+8]; pvarg
0x18004cd0c  call    cs:__imp_VariantClear
0x18004cd12  lea     rcx, [rsp+140h+pvarg]; this
0x18004cd17  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18004cd1c  movups  xmmword ptr [rsp+140h+pvarg+8], xmm6
0x18004cd21  movsd   [rsp+140h+var_F0], xmm7
0x18004cd27  lea     rcx, [rbp+40h+var_90]; pvarg
0x18004cd2b  call    cs:__imp_VariantClear
0x18004cd31  movups  xmm0, xmmword ptr [rsp+140h+pvarg+8]
0x18004cd36  movsd   xmm1, [rsp+140h+var_F0]
0x18004cd3c  movaps  xmmword ptr [rbp+40h+var_90], xmm0
0x18004cd40  movsd   qword ptr [rbp+40h+var_90+10h], xmm1
0x18004cd45  mov     rax, [rsi]
0x18004cd48  lea     r8, [rbp+40h+var_90]
0x18004cd4c  mov     rdx, [rsp+140h+var_110]
0x18004cd51  mov     rcx, rsi
0x18004cd54  mov     rax, [rax+38h]
0x18004cd58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cd5d  mov     r14d, eax
0x18004cd60  test    eax, eax
0x18004cd62  jnz     short loc_18004CD85
0x18004cd64  lea     rcx, [rbp+40h+Src]
0x18004cd68  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004cd6d  nop
0x18004cd6e  lea     rcx, [rsp+140h+var_110]
0x18004cd73  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004cd78  add     rbx, 20h ; ' '
0x18004cd7c  add     rdi, 20h ; ' '
0x18004cd80  jmp     loc_18004CC75
0x18004cd85  lea     rax, [rbp+40h+Src]
0x18004cd89  cmp     [rbp+40h+var_58], 7
0x18004cd8e  cmova   rax, [rbp+40h+Src]
0x18004cd93  mov     rcx, [rbp+48h]; this
0x18004cd97  mov     [rsp+140h+var_118], rax; char *
0x18004cd9c  lea     rax, aErrorAddingSch; "Error adding schema '%ls'"
0x18004cda3  mov     qword ptr [rsp+140h+var_120], rax; int
0x18004cda8  mov     r9d, r14d; char *
0x18004cdab  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x18004cdb2  mov     edx, 57h ; 'W'; void *
0x18004cdb7  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004cdbc  mov     ecx, r14d; this
0x18004cdbf  call    ?GetXmlErrorAndThrow@XmlHelperModern@EapHost@@YAXJ@Z; EapHost::XmlHelperModern::GetXmlErrorAndThrow(long)
0x18004cdc5  lea     rcx, [rsp+140h+var_D8+8]; pvarg
0x18004cdca  call    cs:__imp_VariantInit
0x18004cdd0  nop
0x18004cdd1  lea     rcx, [rsp+140h+var_D8+8]; pvarg
0x18004cdd6  call    cs:__imp_VariantInit
0x18004cddc  mov     eax, 0Dh
0x18004cde1  mov     word ptr [rsp+140h+var_D8+8], ax
0x18004cde6  mov     qword ptr [rsp+140h+var_D8+10h], rsi
0x18004cdeb  mov     rax, [rsi]
0x18004cdee  mov     rcx, rsi
0x18004cdf1  mov     rax, [rax+8]
0x18004cdf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cdfa  movups  xmm0, xmmword ptr [rsp+140h+var_D8+8]
0x18004cdff  movaps  xmmword ptr [rbp+40h+var_90], xmm0
0x18004ce03  movsd   xmm1, [rbp+40h+var_C0]
0x18004ce08  movsd   qword ptr [rbp+40h+var_90+10h], xmm1
0x18004ce0d  mov     rax, [r12]
0x18004ce11  lea     rdx, [rbp+40h+var_90]
0x18004ce15  mov     rcx, r12
0x18004ce18  mov     rax, [rax+270h]
0x18004ce1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce24  test    eax, eax
0x18004ce26  jz      short loc_18004CE30
0x18004ce28  mov     ecx, eax; this
0x18004ce2a  call    ?GetXmlErrorAndThrow@XmlHelperModern@EapHost@@YAXJ@Z; EapHost::XmlHelperModern::GetXmlErrorAndThrow(long)
0x18004ce30  lea     rcx, [rsp+140h+var_D8+8]; pvarg
0x18004ce35  call    cs:__imp_VariantClear
0x18004ce3b  nop
0x18004ce3c  lea     rcx, [rsp+140h+var_E8]
0x18004ce41  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004ce46  nop
0x18004ce47  lea     rcx, [rsp+140h+var_E0]
0x18004ce4c  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x18004ce51  nop
0x18004ce52  lea     rcx, [rsp+140h+pvarg+8]; pvarg
0x18004ce57  call    cs:__imp_VariantClear
0x18004ce5d  nop
0x18004ce5e  lea     rcx, [rsp+140h+var_D8]
0x18004ce63  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004ce68  nop
0x18004ce69  mov     rcx, [rbp+40h+var_50]
0x18004ce6d  xor     rcx, rsp; StackCookie
0x18004ce70  call    __security_check_cookie
0x18004ce75  lea     r11, [rsp+140h+var_20]
0x18004ce7d  mov     rbx, [r11+40h]
0x18004ce81  mov     rsi, [r11+48h]
0x18004ce85  movaps  xmm6, xmmword ptr [r11-10h]
0x18004ce8a  movaps  xmm7, xmmword ptr [r11-20h]
0x18004ce8f  mov     rsp, r11
0x18004ce92  pop     r15
0x18004ce94  pop     r14
0x18004ce96  pop     r12
0x18004ce98  pop     rdi
0x18004ce99  pop     rbp
0x18004ce9a  retn
```

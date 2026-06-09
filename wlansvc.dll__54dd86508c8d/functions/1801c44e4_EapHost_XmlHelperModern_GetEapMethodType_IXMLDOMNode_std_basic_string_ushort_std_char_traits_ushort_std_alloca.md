# EapHost::XmlHelperModern::GetEapMethodType(IXMLDOMNode *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1801c44e4`
- end: `0x1801c49f9`
- name: `?GetEapMethodType@XmlHelperModern@EapHost@@YA?AVEapMethodType@2@PEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1301`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ecd48`

## callees

- `0x18000d650`
- `0x18001a0d0`
- `0x1800360b8`
- `0x180066c60`
- `0x1800b2a88`
- `0x1800c6cd0`
- `0x1800e1564`
- `0x1800f0890`
- `0x1800f0a0c`
- `0x1800f2204`
- `0x180106340`
- `0x1801222fc`
- `0x1801c44e4`
- `0x1801c4ccc`
- `0x1801c54dc`
- `0x1801c5568`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1801c4628`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1801c4628`
- `OLEAUT32!__imp_VariantInit` at `0x1801c466f`
- `OLEAUT32!__imp_VariantInit` at `0x1801c466f`
- `OLEAUT32!__imp_VariantClear` at `0x1801c499f`
- `OLEAUT32!__imp_VariantClear` at `0x1801c499f`

## string_xrefs

- `0x1801c45ef`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x1801c4658`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x1801c46e7`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x1801c4772`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x1801c47ff`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x1801c488f`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x1801c495e`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x1801c4676`: `./eapCommon:Type`
- `0x1801c46ff`: `./eapCommon:AuthorId`
- `0x1801c478c`: `./eapCommon:VendorId`
- `0x1801c4819`: `./eapCommon:VendorType`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall EapHost::XmlHelperModern::GetEapMethodType(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rdx
  signed int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rcx
  int bVal; // r15d
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  LONG lVal; // r12d
  LONG v16; // r14d
  __int64 v17; // rax
  char Value; // bl
  __int64 v19; // rdx
  __int64 v20; // rcx
  LONG v21; // edi
  __int64 v22; // rax
  char v23; // bl
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rcx
  int lpBuffer; // [rsp+20h] [rbp-E0h]
  const char *nSize; // [rsp+28h] [rbp-D8h]
  char v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  LONG v33; // [rsp+68h] [rbp-98h] BYREF
  LONG v34; // [rsp+70h] [rbp-90h] BYREF
  LONG v35; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v36[3]; // [rsp+80h] [rbp-80h] BYREF
  char v37; // [rsp+98h] [rbp-68h]
  __int64 v38; // [rsp+9Ch] [rbp-64h]
  int v39; // [rsp+A8h] [rbp-58h]
  _QWORD Src[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v41[32]; // [rsp+D0h] [rbp-30h] BYREF
  char v42[16]; // [rsp+F0h] [rbp-10h] BYREF
  char *v43; // [rsp+100h] [rbp+0h]
  __int64 v44; // [rsp+108h] [rbp+8h]
  LONG *v45; // [rsp+110h] [rbp+10h]
  __int64 v46; // [rsp+118h] [rbp+18h]
  LONG *v47; // [rsp+120h] [rbp+20h]
  __int64 v48; // [rsp+128h] [rbp+28h]
  LONG *v49; // [rsp+130h] [rbp+30h]
  __int64 v50; // [rsp+138h] [rbp+38h]
  WCHAR Buffer[1024]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+988h] [rbp+888h]

  v36[0] = a1;
  v37 = 0;
  v38 = 0;
  v36[2] = &EapHost::EapMethodType::`vftable';
  v39 = 0;
  v31 = 0;
  std::wstring::wstring(Src, L".//");
  std::wstring::append(Src);
  std::wstring::_Append<unsigned short>(Src);
  std::wstring::_Append<unsigned short>(Src);
  v4 = Src;
  if ( Src[3] > 7u )
    v4 = (_QWORD *)Src[0];
  wil::make_bstr(v36, v4);
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a2 + 296LL))(a2, v36[0], &v31);
  if ( v5 == 1 )
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
      (const char *)0x80420019LL,
      (int)"EapMethodType node missing",
      nSize);
  if ( v5 < 0 )
  {
    FormatMessageW(0x1200u, 0, v5, 0, Buffer, 0x400u, 0);
    if ( (byte_1802A3581 & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(eaphost_Context, XMLNodeFailedEvent, Buffer);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
      (const char *)(unsigned int)v5,
      lpBuffer);
  }
  VariantInit(&pvarg);
  v6 = std::wstring::wstring(v41, L"./eapCommon:Type");
  LOBYTE(v7) = 1;
  EapHost::XmlHelperModern::FindAndGetValue(v31, v6, v7, &pvarg);
  std::pair<std::wstring,void *>::~pair<std::wstring,void *>(v41);
  if ( (int)EapHost::XmlHelperModern::VariantConvert(&pvarg, 17) < 0 )
  {
    if ( (byte_1802A3581 & 1) != 0 )
      McTemplateU0s_EventWriteTransfer(v9, v8, "Type");
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
      (const char *)0x80420019LL,
      (int)"Datatype mismatch for Type",
      nSize);
  }
  bVal = pvarg.bVal;
  v11 = std::wstring::wstring(v41, L"./eapCommon:AuthorId");
  LOBYTE(v12) = 1;
  EapHost::XmlHelperModern::FindAndGetValue(v31, v11, v12, &pvarg);
  std::pair<std::wstring,void *>::~pair<std::wstring,void *>(v41);
  if ( (int)EapHost::XmlHelperModern::VariantConvert(&pvarg, 3) < 0 )
  {
    if ( (byte_1802A3581 & 1) != 0 )
      McTemplateU0s_EventWriteTransfer(v14, v13, "AuthorId");
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
      (const char *)0x80420019LL,
      (int)"Datatype mismatch for AuthorId",
      nSize);
  }
  lVal = pvarg.lVal;
  v16 = 0;
  v17 = std::wstring::wstring(v41, L"./eapCommon:VendorId");
  Value = EapHost::XmlHelperModern::FindAndGetValue(v31, v17, 0, &pvarg);
  std::pair<std::wstring,void *>::~pair<std::wstring,void *>(v41);
  if ( Value )
  {
    if ( (int)EapHost::XmlHelperModern::VariantConvert(&pvarg, 3) < 0 )
    {
      if ( (byte_1802A3581 & 1) != 0 )
        McTemplateU0s_EventWriteTransfer(v20, v19, "VendorId");
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x207,
        (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
        (const char *)0x80420019LL,
        (int)"Datatype mismatch for VendorId",
        nSize);
    }
    v16 = pvarg.lVal;
  }
  v21 = 0;
  v22 = std::wstring::wstring(v41, L"./eapCommon:VendorType");
  v23 = EapHost::XmlHelperModern::FindAndGetValue(v31, v22, 0, &pvarg);
  std::pair<std::wstring,void *>::~pair<std::wstring,void *>(v41);
  if ( v23 )
  {
    if ( (int)EapHost::XmlHelperModern::VariantConvert(&pvarg, 3) < 0 )
    {
      if ( (byte_1802A3581 & 1) != 0 )
        McTemplateU0s_EventWriteTransfer(v26, v25, "VendorType");
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x213,
        (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
        (const char *)0x80420019LL,
        (int)"Datatype mismatch for VendorType",
        nSize);
    }
    v21 = pvarg.lVal;
  }
  if ( (unsigned __int8)bVal < 4u )
    goto LABEL_32;
  if ( (_BYTE)bVal != 0xFE )
  {
    if ( !v16 && !v21 )
      goto LABEL_37;
LABEL_32:
    if ( (byte_1802A3581 & 1) != 0 )
    {
      v35 = v21;
      v34 = v16;
      v33 = lVal;
      v30 = bVal;
      v43 = &v30;
      v44 = 1;
      v45 = &v33;
      v46 = 4;
      v47 = &v34;
      v48 = 4;
      v49 = &v35;
      v50 = 4;
      McGenEventWrite_EventWriteTransfer(eaphost_Context, XMLConfigError, v24, 5, v42);
    }
    LODWORD(nSize) = bVal;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x21E,
      (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
      (const char *)0x80420019LL,
      (int)"Bad method: type(%d), VendorId(%d), VendorType(%d)",
      nSize,
      v16,
      v21);
  }
  if ( !v21 )
    goto LABEL_32;
LABEL_37:
  *(_BYTE *)(a1 + 8) = bVal;
  *(_DWORD *)(a1 + 12) = v16;
  *(_DWORD *)(a1 + 16) = v21;
  *(_QWORD *)a1 = &EapHost::EapMethodType::`vftable';
  *(_DWORD *)(a1 + 24) = lVal;
  VariantClear(&pvarg);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v36);
  std::pair<std::wstring,void *>::~pair<std::wstring,void *>(Src);
  if ( v31 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v31);
  return a1;
}

```

## disassembly

```asm
0x1801c44e4  mov     [rsp-8+arg_18], rbx
0x1801c44e9  push    rbp
0x1801c44ea  push    rsi
0x1801c44eb  push    rdi
0x1801c44ec  push    r12
0x1801c44ee  push    r13
0x1801c44f0  push    r14
0x1801c44f2  push    r15
0x1801c44f4  lea     rbp, [rsp-850h]
0x1801c44fc  sub     rsp, 950h
0x1801c4503  mov     rax, cs:__security_cookie
0x1801c450a  xor     rax, rsp
0x1801c450d  mov     [rbp+880h+var_40], rax
0x1801c4514  mov     rbx, r8
0x1801c4517  mov     rdi, rdx
0x1801c451a  mov     rsi, rcx
0x1801c451d  mov     [rbp+880h+var_900], rcx
0x1801c4521  xor     r13d, r13d
0x1801c4524  mov     [rbp+880h+var_8E8], r13b
0x1801c4528  mov     [rbp+880h+var_8E4], r13
0x1801c452c  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x1801c4533  mov     [rbp+880h+var_8F0], rax
0x1801c4537  mov     [rbp+880h+var_8D8], r13d
0x1801c453b  mov     [rsp+980h+var_938], r13
0x1801c4540  lea     rdx, asc_18025DE30; ".//"
0x1801c4547  lea     rcx, [rbp+880h+Src]
0x1801c454b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801c4550  nop
0x1801c4551  mov     rdx, rbx
0x1801c4554  lea     rcx, [rbp+880h+Src]; Src
0x1801c4558  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x1801c455d  lea     r14d, [r13+1]
0x1801c4561  mov     r8d, r14d
0x1801c4564  lea     rdx, asc_180244250; ":"
0x1801c456b  lea     rcx, [rbp+880h+Src]; Src
0x1801c456f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1801c4574  lea     r8d, [r13+9]
0x1801c4578  lea     rdx, aEapmethod; "EapMethod"
0x1801c457f  lea     rcx, [rbp+880h+Src]; Src
0x1801c4583  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1801c4588  lea     rdx, [rbp+880h+Src]
0x1801c458c  cmp     [rbp+880h+var_8B8], 7
0x1801c4591  cmova   rdx, [rbp+880h+Src]
0x1801c4596  lea     rcx, [rbp+880h+var_900]
0x1801c459a  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1801c459f  nop
0x1801c45a0  mov     rax, [rdi]
0x1801c45a3  mov     rbx, [rax+128h]
0x1801c45aa  cmp     [rsp+980h+var_938], r13
0x1801c45af  jz      short loc_1801C45BB
0x1801c45b1  lea     rcx, [rsp+980h+var_938]
0x1801c45b6  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x1801c45bb  lea     r8, [rsp+980h+var_938]
0x1801c45c0  mov     rdx, [rbp+880h+var_900]
0x1801c45c4  mov     rcx, rdi
0x1801c45c7  mov     rax, rbx
0x1801c45ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c45cf  mov     ebx, eax
0x1801c45d1  cmp     eax, r14d
0x1801c45d4  jnz     short loc_1801C4601
0x1801c45d6  mov     rcx, [rbp+888h]; this
0x1801c45dd  lea     rax, aEapmethodtypeN; "EapMethodType node missing"
0x1801c45e4  mov     [rsp+980h+lpBuffer], rax; int
0x1801c45e9  mov     r9d, 80420019h; char *
0x1801c45ef  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x1801c45f6  mov     edx, 1E2h; void *
0x1801c45fb  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801c4601  test    ebx, ebx
0x1801c4603  jns     short loc_1801C466A
0x1801c4605  mov     [rsp+980h+Arguments], r13; Arguments
0x1801c460a  mov     dword ptr [rsp+980h+nSize], 400h; nSize
0x1801c4612  lea     rax, [rbp+880h+Buffer]
0x1801c4616  mov     [rsp+980h+lpBuffer], rax; int
0x1801c461b  xor     r9d, r9d; dwLanguageId
0x1801c461e  mov     r8d, ebx; dwMessageId
0x1801c4621  xor     edx, edx; lpSource
0x1801c4623  mov     ecx, 1200h; dwFlags
0x1801c4628  call    cs:__imp_FormatMessageW
0x1801c462e  test    cs:byte_1802A3581, r14b
0x1801c4635  jz      short loc_1801C464E
0x1801c4637  lea     r8, [rbp+880h+Buffer]
0x1801c463b  lea     rdx, XMLNodeFailedEvent
0x1801c4642  lea     rcx, eaphost_Context
0x1801c4649  call    McTemplateU0z_EventWriteTransfer
0x1801c464e  mov     rcx, [rbp+888h]; this
0x1801c4655  mov     r9d, ebx; char *
0x1801c4658  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x1801c465f  mov     edx, 1EAh; void *
0x1801c4664  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801c466a  lea     rcx, [rsp+980h+pvarg]; pvarg
0x1801c466f  call    cs:__imp_VariantInit
0x1801c4675  nop
0x1801c4676  lea     rdx, aEapcommonType; "./eapCommon:Type"
0x1801c467d  lea     rcx, [rbp+880h+var_8B0]
0x1801c4681  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801c4686  nop
0x1801c4687  lea     r9, [rsp+980h+pvarg]
0x1801c468c  mov     r8b, r14b
0x1801c468f  mov     rdx, rax
0x1801c4692  mov     rcx, [rsp+980h+var_938]
0x1801c4697  call    ?FindAndGetValue@XmlHelperModern@EapHost@@YA_NPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; EapHost::XmlHelperModern::FindAndGetValue(IXMLDOMNode *,std::wstring const &,bool,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &)
0x1801c469c  nop
0x1801c469d  lea     rcx, [rbp+880h+var_8B0]; void *
0x1801c46a1  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@QEAA@XZ; std::pair<std::wstring,void *>::~pair<std::wstring,void *>(void)
0x1801c46a6  mov     edx, 11h; int
0x1801c46ab  lea     rcx, [rsp+980h+pvarg]; pvarSrc
0x1801c46b0  call    ?VariantConvert@XmlHelperModern@EapHost@@YAJAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@G@Z; EapHost::XmlHelperModern::VariantConvert(wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &,ushort)
0x1801c46b5  test    eax, eax
0x1801c46b7  jns     short loc_1801C46F9
0x1801c46b9  test    cs:byte_1802A3581, r14b
0x1801c46c0  jz      short loc_1801C46CE
0x1801c46c2  lea     r8, aType_0; "Type"
0x1801c46c9  call    McTemplateU0s_EventWriteTransfer
0x1801c46ce  mov     rcx, [rbp+888h]; this
0x1801c46d5  lea     rax, aDatatypeMismat_2; "Datatype mismatch for Type"
0x1801c46dc  mov     [rsp+980h+lpBuffer], rax; int
0x1801c46e1  mov     r9d, 80420019h; char *
0x1801c46e7  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x1801c46ee  mov     edx, 1F3h; void *
0x1801c46f3  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801c46f9  movzx   r15d, byte ptr [rsp+980h+pvarg+8]
0x1801c46ff  lea     rdx, aEapcommonAutho; "./eapCommon:AuthorId"
0x1801c4706  lea     rcx, [rbp+880h+var_8B0]
0x1801c470a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801c470f  nop
0x1801c4710  lea     r9, [rsp+980h+pvarg]
0x1801c4715  mov     r8b, r14b
0x1801c4718  mov     rdx, rax
0x1801c471b  mov     rcx, [rsp+980h+var_938]
0x1801c4720  call    ?FindAndGetValue@XmlHelperModern@EapHost@@YA_NPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; EapHost::XmlHelperModern::FindAndGetValue(IXMLDOMNode *,std::wstring const &,bool,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &)
0x1801c4725  nop
0x1801c4726  lea     rcx, [rbp+880h+var_8B0]; void *
0x1801c472a  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@QEAA@XZ; std::pair<std::wstring,void *>::~pair<std::wstring,void *>(void)
0x1801c472f  mov     edi, 3
0x1801c4734  mov     edx, edi; int
0x1801c4736  lea     rcx, [rsp+980h+pvarg]; pvarSrc
0x1801c473b  call    ?VariantConvert@XmlHelperModern@EapHost@@YAJAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@G@Z; EapHost::XmlHelperModern::VariantConvert(wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &,ushort)
0x1801c4740  test    eax, eax
0x1801c4742  jns     short loc_1801C4784
0x1801c4744  test    cs:byte_1802A3581, r14b
0x1801c474b  jz      short loc_1801C4759
0x1801c474d  lea     r8, aAuthorid; "AuthorId"
0x1801c4754  call    McTemplateU0s_EventWriteTransfer
0x1801c4759  mov     rcx, [rbp+888h]; this
0x1801c4760  lea     rax, aDatatypeMismat; "Datatype mismatch for AuthorId"
0x1801c4767  mov     [rsp+980h+lpBuffer], rax; int
0x1801c476c  mov     r9d, 80420019h; char *
0x1801c4772  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x1801c4779  mov     edx, 1FCh; void *
0x1801c477e  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801c4784  mov     r12d, dword ptr [rsp+980h+pvarg+8]
0x1801c4789  mov     r14d, r13d
0x1801c478c  lea     rdx, aEapcommonVendo; "./eapCommon:VendorId"
0x1801c4793  lea     rcx, [rbp+880h+var_8B0]
0x1801c4797  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801c479c  nop
0x1801c479d  lea     r9, [rsp+980h+pvarg]
0x1801c47a2  xor     r8d, r8d
0x1801c47a5  mov     rdx, rax
0x1801c47a8  mov     rcx, [rsp+980h+var_938]
0x1801c47ad  call    ?FindAndGetValue@XmlHelperModern@EapHost@@YA_NPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; EapHost::XmlHelperModern::FindAndGetValue(IXMLDOMNode *,std::wstring const &,bool,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &)
0x1801c47b2  mov     bl, al
0x1801c47b4  lea     rcx, [rbp+880h+var_8B0]; void *
0x1801c47b8  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@QEAA@XZ; std::pair<std::wstring,void *>::~pair<std::wstring,void *>(void)
0x1801c47bd  test    bl, bl
0x1801c47bf  jz      short loc_1801C4816
0x1801c47c1  mov     edx, edi; int
0x1801c47c3  lea     rcx, [rsp+980h+pvarg]; pvarSrc
0x1801c47c8  call    ?VariantConvert@XmlHelperModern@EapHost@@YAJAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@G@Z; EapHost::XmlHelperModern::VariantConvert(wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &,ushort)
0x1801c47cd  test    eax, eax
0x1801c47cf  jns     short loc_1801C4811
0x1801c47d1  test    cs:byte_1802A3581, 1
0x1801c47d8  jz      short loc_1801C47E6
0x1801c47da  lea     r8, aVendorid; "VendorId"
0x1801c47e1  call    McTemplateU0s_EventWriteTransfer
0x1801c47e6  mov     rcx, [rbp+888h]; this
0x1801c47ed  lea     rax, aDatatypeMismat_0; "Datatype mismatch for VendorId"
0x1801c47f4  mov     [rsp+980h+lpBuffer], rax; int
0x1801c47f9  mov     r9d, 80420019h; char *
0x1801c47ff  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x1801c4806  mov     edx, 207h; void *
0x1801c480b  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801c4811  mov     r14d, dword ptr [rsp+980h+pvarg+8]
0x1801c4816  mov     edi, r13d
0x1801c4819  lea     rdx, aEapcommonVendo_0; "./eapCommon:VendorType"
0x1801c4820  lea     rcx, [rbp+880h+var_8B0]
0x1801c4824  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801c4829  nop
0x1801c482a  lea     r9, [rsp+980h+pvarg]
0x1801c482f  xor     r8d, r8d
0x1801c4832  mov     rdx, rax
0x1801c4835  mov     rcx, [rsp+980h+var_938]
0x1801c483a  call    ?FindAndGetValue@XmlHelperModern@EapHost@@YA_NPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; EapHost::XmlHelperModern::FindAndGetValue(IXMLDOMNode *,std::wstring const &,bool,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &)
0x1801c483f  mov     bl, al
0x1801c4841  lea     rcx, [rbp+880h+var_8B0]; void *
0x1801c4845  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@QEAA@XZ; std::pair<std::wstring,void *>::~pair<std::wstring,void *>(void)
0x1801c484a  test    bl, bl
0x1801c484c  jz      short loc_1801C48A5
0x1801c484e  mov     edx, 3; int
0x1801c4853  lea     rcx, [rsp+980h+pvarg]; pvarSrc
0x1801c4858  call    ?VariantConvert@XmlHelperModern@EapHost@@YAJAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@G@Z; EapHost::XmlHelperModern::VariantConvert(wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &,ushort)
0x1801c485d  test    eax, eax
0x1801c485f  jns     short loc_1801C48A1
0x1801c4861  test    cs:byte_1802A3581, 1
0x1801c4868  jz      short loc_1801C4876
0x1801c486a  lea     r8, aVendortype; "VendorType"
0x1801c4871  call    McTemplateU0s_EventWriteTransfer
0x1801c4876  mov     rcx, [rbp+888h]; this
0x1801c487d  lea     rax, aDatatypeMismat_1; "Datatype mismatch for VendorType"
0x1801c4884  mov     [rsp+980h+lpBuffer], rax; int
0x1801c4889  mov     r9d, 80420019h; char *
0x1801c488f  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x1801c4896  mov     edx, 213h; void *
0x1801c489b  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801c48a1  mov     edi, dword ptr [rsp+980h+pvarg+8]
0x1801c48a5  mov     ecx, 4
0x1801c48aa  cmp     r15b, cl
0x1801c48ad  jb      short loc_1801C48C1
0x1801c48af  cmp     r15b, 0FEh
0x1801c48b3  jnz     loc_1801C4970
0x1801c48b9  test    edi, edi
0x1801c48bb  jnz     loc_1801C4981
0x1801c48c1  test    cs:byte_1802A3581, 1
0x1801c48c8  jz      short loc_1801C4937
0x1801c48ca  mov     [rsp+980h+var_908], edi
0x1801c48ce  mov     [rsp+980h+var_910], r14d
0x1801c48d3  mov     [rsp+980h+var_918], r12d
0x1801c48d8  mov     [rsp+980h+var_940], r15b
0x1801c48dd  lea     rax, [rsp+980h+var_940]
0x1801c48e2  mov     [rbp+880h+var_880], rax
0x1801c48e6  mov     [rbp+880h+var_878], 1
0x1801c48ee  lea     rax, [rsp+980h+var_918]
0x1801c48f3  mov     [rbp+880h+var_870], rax
0x1801c48f7  mov     [rbp+880h+var_868], rcx
0x1801c48fb  lea     rax, [rsp+980h+var_910]
0x1801c4900  mov     [rbp+880h+var_860], rax
0x1801c4904  mov     [rbp+880h+var_858], rcx
0x1801c4908  lea     rax, [rsp+980h+var_908]
0x1801c490d  mov     [rbp+880h+var_850], rax
0x1801c4911  mov     [rbp+880h+var_848], rcx
0x1801c4915  lea     rax, [rbp+880h+var_890]
0x1801c4919  mov     [rsp+980h+lpBuffer], rax
0x1801c491e  mov     r9d, 5
0x1801c4924  lea     rdx, XMLConfigError
0x1801c492b  lea     rcx, eaphost_Context
0x1801c4932  call    McGenEventWrite_EventWriteTransfer
0x1801c4937  mov     rcx, [rbp+888h]; this
0x1801c493e  mov     [rsp+980h+var_948], edi
0x1801c4942  mov     dword ptr [rsp+980h+Arguments], r14d
0x1801c4947  mov     dword ptr [rsp+980h+nSize], r15d; char *
0x1801c494c  lea     rax, aBadMethodTypeD; "Bad method: type(%d), VendorId(%d), Ven"...
0x1801c4953  mov     [rsp+980h+lpBuffer], rax; int
0x1801c4958  mov     r9d, 80420019h; char *
0x1801c495e  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x1801c4965  mov     edx, 21Eh; void *
0x1801c496a  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801c4970  test    r14d, r14d
0x1801c4973  jnz     loc_1801C48C1
0x1801c4979  test    edi, edi
0x1801c497b  jnz     loc_1801C48C1
0x1801c4981  mov     [rsi+8], r15b
0x1801c4985  mov     [rsi+0Ch], r14d
0x1801c4989  mov     [rsi+10h], edi
0x1801c498c  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x1801c4993  mov     [rsi], rax
0x1801c4996  mov     [rsi+18h], r12d
0x1801c499a  lea     rcx, [rsp+980h+pvarg]; pvarg
0x1801c499f  call    cs:__imp_VariantClear
0x1801c49a5  nop
0x1801c49a6  lea     rcx, [rbp+880h+var_900]
0x1801c49aa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1801c49af  nop
0x1801c49b0  lea     rcx, [rbp+880h+Src]; void *
0x1801c49b4  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@QEAA@XZ; std::pair<std::wstring,void *>::~pair<std::wstring,void *>(void)
0x1801c49b9  nop
0x1801c49ba  cmp     [rsp+980h+var_938], r13
0x1801c49bf  jz      short loc_1801C49CC
0x1801c49c1  lea     rcx, [rsp+980h+var_938]
0x1801c49c6  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x1801c49cb  nop
0x1801c49cc  mov     rax, rsi
0x1801c49cf  mov     rcx, [rbp+880h+var_40]
0x1801c49d6  xor     rcx, rsp; StackCookie
0x1801c49d9  call    __security_check_cookie
0x1801c49de  mov     rbx, [rsp+980h+arg_18]
0x1801c49e6  add     rsp, 950h
0x1801c49ed  pop     r15
0x1801c49ef  pop     r14
0x1801c49f1  pop     r13
0x1801c49f3  pop     r12
0x1801c49f5  pop     rdi
0x1801c49f6  pop     rsi
0x1801c49f7  pop     rbp
0x1801c49f8  retn
```

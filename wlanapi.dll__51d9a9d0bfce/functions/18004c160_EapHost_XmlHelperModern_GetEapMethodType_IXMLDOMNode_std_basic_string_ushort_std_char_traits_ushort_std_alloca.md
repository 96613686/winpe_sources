# EapHost::XmlHelperModern::GetEapMethodType(IXMLDOMNode *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004c160`
- end: `0x18004c6b7`
- name: `?GetEapMethodType@XmlHelperModern@EapHost@@YA?AVEapMethodType@2@PEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1367`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004bb34`

## callees

- `0x180019a20`
- `0x1800398dc`
- `0x18003a098`
- `0x18003a124`
- `0x18003a638`
- `0x18004b89c`
- `0x18004bfe4`
- `0x18004c160`
- `0x18004cf90`
- `0x18004cfb0`
- `0x18004d344`
- `0x18004d51c`
- `0x18004dc1c`
- `0x18004dca8`
- `0x18004dd00`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004c2c1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004c2c1`
- `OLEAUT32!__imp_VariantInit` at `0x18004c334`
- `OLEAUT32!__imp_VariantInit` at `0x18004c334`
- `OLEAUT32!__imp_VariantClear` at `0x18004c65d`
- `OLEAUT32!__imp_VariantClear` at `0x18004c65d`

## string_xrefs

- `0x18004c284`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x18004c31d`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x18004c3ac`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x18004c437`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x18004c4c4`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x18004c554`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x18004c61c`: `onecoreuap\private\net\inc\eaphost\xmlhelpermodern.h`
- `0x18004c33b`: `./eapCommon:Type`
- `0x18004c3c4`: `./eapCommon:AuthorId`
- `0x18004c451`: `./eapCommon:VendorId`
- `0x18004c4de`: `./eapCommon:VendorType`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall EapHost::XmlHelperModern::GetEapMethodType(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rdx
  signed int v5; // ebx
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rcx
  int bVal; // r15d
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rcx
  LONG lVal; // r12d
  LONG v18; // r14d
  __int64 v19; // rax
  char Value; // bl
  __int64 v21; // rdx
  __int64 v22; // rcx
  LONG v23; // esi
  __int64 v24; // rax
  char v25; // bl
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rcx
  int lpBuffer; // [rsp+20h] [rbp-E0h]
  const char *nSize; // [rsp+28h] [rbp-D8h]
  char v32; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  LONG v35; // [rsp+68h] [rbp-98h] BYREF
  LONG v36; // [rsp+70h] [rbp-90h] BYREF
  LONG v37; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v38[3]; // [rsp+80h] [rbp-80h] BYREF
  char v39; // [rsp+98h] [rbp-68h]
  __int64 v40; // [rsp+9Ch] [rbp-64h]
  int v41; // [rsp+A8h] [rbp-58h]
  int v42[4]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR *v43; // [rsp+C0h] [rbp-40h]
  int v44; // [rsp+C8h] [rbp-38h]
  int v45; // [rsp+CCh] [rbp-34h]
  _QWORD Src[4]; // [rsp+D0h] [rbp-30h] BYREF
  char v47[16]; // [rsp+F0h] [rbp-10h] BYREF
  char *v48; // [rsp+100h] [rbp+0h]
  __int64 v49; // [rsp+108h] [rbp+8h]
  LONG *v50; // [rsp+110h] [rbp+10h]
  __int64 v51; // [rsp+118h] [rbp+18h]
  LONG *v52; // [rsp+120h] [rbp+20h]
  __int64 v53; // [rsp+128h] [rbp+28h]
  LONG *v54; // [rsp+130h] [rbp+30h]
  __int64 v55; // [rsp+138h] [rbp+38h]
  WCHAR Buffer[1024]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+988h] [rbp+888h]

  v38[0] = a1;
  v39 = 0;
  v40 = 0;
  v38[2] = &EapHost::EapMethodType::`vftable';
  v41 = 0;
  v33 = 0;
  std::wstring::wstring(Src, L".//");
  std::wstring::_Append<unsigned short>(Src);
  std::_WChar_traits<unsigned short>::length(L":");
  std::wstring::_Append<unsigned short>(Src);
  std::_WChar_traits<unsigned short>::length(L"EapMethod");
  std::wstring::_Append<unsigned short>(Src);
  v4 = Src;
  if ( Src[3] > 7u )
    v4 = (_QWORD *)Src[0];
  wil::make_bstr(v38, v4);
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a2 + 296LL))(a2, v38[0], &v33);
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
    if ( (byte_180085041 & 1) != 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( Buffer[v7] );
      v43 = Buffer;
      v44 = 2 * v7 + 2;
      v45 = 0;
      McGenEventWrite_EventWriteTransfer(Buffer, XMLNodeFailedEvent, v6, 2, v42);
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
      (const char *)(unsigned int)v5,
      lpBuffer);
  }
  VariantInit(&pvarg);
  v8 = std::wstring::wstring(v42, L"./eapCommon:Type");
  LOBYTE(v9) = 1;
  EapHost::XmlHelperModern::FindAndGetValue(v33, v8, v9, &pvarg);
  std::wstring::~wstring(v42);
  if ( (int)EapHost::XmlHelperModern::VariantConvert(&pvarg, 17) < 0 )
  {
    if ( (byte_180085041 & 1) != 0 )
      McTemplateU0s_EventWriteTransfer(v11, v10, "Type");
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
      (const char *)0x80420019LL,
      (int)"Datatype mismatch for Type",
      nSize);
  }
  bVal = pvarg.bVal;
  v13 = std::wstring::wstring(v42, L"./eapCommon:AuthorId");
  LOBYTE(v14) = 1;
  EapHost::XmlHelperModern::FindAndGetValue(v33, v13, v14, &pvarg);
  std::wstring::~wstring(v42);
  if ( (int)EapHost::XmlHelperModern::VariantConvert(&pvarg, 3) < 0 )
  {
    if ( (byte_180085041 & 1) != 0 )
      McTemplateU0s_EventWriteTransfer(v16, v15, "AuthorId");
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x1FC,
      (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
      (const char *)0x80420019LL,
      (int)"Datatype mismatch for AuthorId",
      nSize);
  }
  lVal = pvarg.lVal;
  v18 = 0;
  v19 = std::wstring::wstring(v42, L"./eapCommon:VendorId");
  Value = EapHost::XmlHelperModern::FindAndGetValue(v33, v19, 0, &pvarg);
  std::wstring::~wstring(v42);
  if ( Value )
  {
    if ( (int)EapHost::XmlHelperModern::VariantConvert(&pvarg, 3) < 0 )
    {
      if ( (byte_180085041 & 1) != 0 )
        McTemplateU0s_EventWriteTransfer(v22, v21, "VendorId");
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x207,
        (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
        (const char *)0x80420019LL,
        (int)"Datatype mismatch for VendorId",
        nSize);
    }
    v18 = pvarg.lVal;
  }
  v23 = 0;
  v24 = std::wstring::wstring(v42, L"./eapCommon:VendorType");
  v25 = EapHost::XmlHelperModern::FindAndGetValue(v33, v24, 0, &pvarg);
  std::wstring::~wstring(v42);
  if ( v25 )
  {
    if ( (int)EapHost::XmlHelperModern::VariantConvert(&pvarg, 3) < 0 )
    {
      if ( (byte_180085041 & 1) != 0 )
        McTemplateU0s_EventWriteTransfer(v28, v27, "VendorType");
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x213,
        (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
        (const char *)0x80420019LL,
        (int)"Datatype mismatch for VendorType",
        nSize);
    }
    v23 = pvarg.lVal;
  }
  if ( (unsigned __int8)bVal < 4u )
    goto LABEL_34;
  if ( (_BYTE)bVal != 0xFE )
  {
    if ( !v18 && !v23 )
      goto LABEL_39;
LABEL_34:
    if ( (byte_180085041 & 1) != 0 )
    {
      v37 = v23;
      v36 = v18;
      v35 = lVal;
      v32 = bVal;
      v48 = &v32;
      v49 = 1;
      v50 = &v35;
      v51 = 4;
      v52 = &v36;
      v53 = 4;
      v54 = &v37;
      v55 = 4;
      McGenEventWrite_EventWriteTransfer(4, XMLConfigError, v26, 5, v47);
    }
    LODWORD(nSize) = bVal;
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x21E,
      (unsigned int)"onecoreuap\\private\\net\\inc\\eaphost\\xmlhelpermodern.h",
      (const char *)0x80420019LL,
      (int)"Bad method: type(%d), VendorId(%d), VendorType(%d)",
      nSize,
      v18,
      v23);
  }
  if ( !v23 )
    goto LABEL_34;
LABEL_39:
  *(_BYTE *)(a1 + 8) = bVal;
  *(_DWORD *)(a1 + 12) = v18;
  *(_DWORD *)(a1 + 16) = v23;
  *(_QWORD *)a1 = &EapHost::EapMethodType::`vftable';
  *(_DWORD *)(a1 + 24) = lVal;
  VariantClear(&pvarg);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v38);
  std::wstring::~wstring(Src);
  if ( v33 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v33);
  return a1;
}

```

## disassembly

```asm
0x18004c160  mov     [rsp-8+arg_18], rbx
0x18004c165  push    rbp
0x18004c166  push    rsi
0x18004c167  push    rdi
0x18004c168  push    r12
0x18004c16a  push    r13
0x18004c16c  push    r14
0x18004c16e  push    r15
0x18004c170  lea     rbp, [rsp-850h]
0x18004c178  sub     rsp, 950h
0x18004c17f  mov     rax, cs:__security_cookie
0x18004c186  xor     rax, rsp
0x18004c189  mov     [rbp+880h+var_40], rax
0x18004c190  mov     rbx, r8
0x18004c193  mov     rsi, rdx
0x18004c196  mov     rdi, rcx
0x18004c199  mov     [rbp+880h+var_900], rcx
0x18004c19d  xor     r13d, r13d
0x18004c1a0  mov     [rbp+880h+var_8E8], r13b
0x18004c1a4  mov     [rbp+880h+var_8E4], r13
0x18004c1a8  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18004c1af  mov     [rbp+880h+var_8F0], rax
0x18004c1b3  mov     [rbp+880h+var_8D8], r13d
0x18004c1b7  mov     [rsp+980h+var_938], r13
0x18004c1bc  lea     rdx, asc_180075250; ".//"
0x18004c1c3  lea     rcx, [rbp+880h+Src]
0x18004c1c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004c1cc  nop
0x18004c1cd  mov     r8, [rbx+10h]
0x18004c1d1  cmp     qword ptr [rbx+18h], 7
0x18004c1d6  jbe     short loc_18004C1DB
0x18004c1d8  mov     rbx, [rbx]
0x18004c1db  mov     rdx, rbx
0x18004c1de  lea     rcx, [rbp+880h+Src]; Src
0x18004c1e2  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004c1e7  lea     rcx, asc_180075258; ":"
0x18004c1ee  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18004c1f3  mov     r8, rax
0x18004c1f6  mov     rdx, rcx
0x18004c1f9  lea     rcx, [rbp+880h+Src]; Src
0x18004c1fd  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004c202  lea     rcx, aEapmethod; "EapMethod"
0x18004c209  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18004c20e  mov     r8, rax
0x18004c211  mov     rdx, rcx
0x18004c214  lea     rcx, [rbp+880h+Src]; Src
0x18004c218  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004c21d  lea     rdx, [rbp+880h+Src]
0x18004c221  cmp     [rbp+880h+var_898], 7
0x18004c226  cmova   rdx, [rbp+880h+Src]
0x18004c22b  lea     rcx, [rbp+880h+var_900]
0x18004c22f  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18004c234  nop
0x18004c235  mov     rax, [rsi]
0x18004c238  mov     rbx, [rax+128h]
0x18004c23f  cmp     [rsp+980h+var_938], r13
0x18004c244  jz      short loc_18004C250
0x18004c246  lea     rcx, [rsp+980h+var_938]
0x18004c24b  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x18004c250  lea     r8, [rsp+980h+var_938]
0x18004c255  mov     rdx, [rbp+880h+var_900]
0x18004c259  mov     rcx, rsi
0x18004c25c  mov     rax, rbx
0x18004c25f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c264  mov     ebx, eax
0x18004c266  cmp     eax, 1
0x18004c269  jnz     short loc_18004C296
0x18004c26b  mov     rcx, [rbp+888h]; this
0x18004c272  lea     rax, aEapmethodtypeN; "EapMethodType node missing"
0x18004c279  mov     [rsp+980h+lpBuffer], rax; int
0x18004c27e  mov     r9d, 80420019h; char *
0x18004c284  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x18004c28b  mov     edx, 1E2h; void *
0x18004c290  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c296  test    ebx, ebx
0x18004c298  jns     loc_18004C32F
0x18004c29e  mov     [rsp+980h+Arguments], r13; Arguments
0x18004c2a3  mov     dword ptr [rsp+980h+nSize], 400h; nSize
0x18004c2ab  lea     rax, [rbp+880h+Buffer]
0x18004c2af  mov     [rsp+980h+lpBuffer], rax; lpBuffer
0x18004c2b4  xor     r9d, r9d; dwLanguageId
0x18004c2b7  mov     r8d, ebx; dwMessageId
0x18004c2ba  xor     edx, edx; lpSource
0x18004c2bc  mov     ecx, 1200h; dwFlags
0x18004c2c1  call    cs:__imp_FormatMessageW
0x18004c2c7  test    cs:byte_180085041, 1
0x18004c2ce  jz      short loc_18004C313
0x18004c2d0  lea     rcx, [rbp+880h+Buffer]
0x18004c2d4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004c2d8  inc     rax
0x18004c2db  cmp     [rcx+rax*2], r13w
0x18004c2e0  jnz     short loc_18004C2D8
0x18004c2e2  lea     eax, ds:2[rax*2]
0x18004c2e9  lea     rcx, [rbp+880h+Buffer]
0x18004c2ed  mov     [rbp+880h+var_8C0], rcx
0x18004c2f1  mov     [rbp+880h+var_8B8], eax
0x18004c2f4  mov     [rbp+880h+var_8B4], r13d
0x18004c2f8  lea     rax, [rbp+880h+var_8D0]
0x18004c2fc  mov     [rsp+980h+lpBuffer], rax; int
0x18004c301  mov     r9d, 2
0x18004c307  lea     rdx, XMLNodeFailedEvent
0x18004c30e  call    McGenEventWrite_EventWriteTransfer
0x18004c313  mov     rcx, [rbp+888h]; this
0x18004c31a  mov     r9d, ebx; char *
0x18004c31d  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x18004c324  mov     edx, 1EAh; void *
0x18004c329  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004c32f  lea     rcx, [rsp+980h+pvarg]; pvarg
0x18004c334  call    cs:__imp_VariantInit
0x18004c33a  nop
0x18004c33b  lea     rdx, aEapcommonType; "./eapCommon:Type"
0x18004c342  lea     rcx, [rbp+880h+var_8D0]
0x18004c346  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004c34b  nop
0x18004c34c  lea     r9, [rsp+980h+pvarg]
0x18004c351  mov     r8b, 1
0x18004c354  mov     rdx, rax
0x18004c357  mov     rcx, [rsp+980h+var_938]
0x18004c35c  call    ?FindAndGetValue@XmlHelperModern@EapHost@@YA_NPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; EapHost::XmlHelperModern::FindAndGetValue(IXMLDOMNode *,std::wstring const &,bool,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &)
0x18004c361  nop
0x18004c362  lea     rcx, [rbp+880h+var_8D0]
0x18004c366  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c36b  mov     edx, 11h; int
0x18004c370  lea     rcx, [rsp+980h+pvarg]; pvarSrc
0x18004c375  call    ?VariantConvert@XmlHelperModern@EapHost@@YAJAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@G@Z; EapHost::XmlHelperModern::VariantConvert(wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &,ushort)
0x18004c37a  test    eax, eax
0x18004c37c  jns     short loc_18004C3BE
0x18004c37e  test    cs:byte_180085041, 1
0x18004c385  jz      short loc_18004C393
0x18004c387  lea     r8, aType_0; "Type"
0x18004c38e  call    McTemplateU0s_EventWriteTransfer
0x18004c393  mov     rcx, [rbp+888h]; this
0x18004c39a  lea     rax, aDatatypeMismat_2; "Datatype mismatch for Type"
0x18004c3a1  mov     [rsp+980h+lpBuffer], rax; int
0x18004c3a6  mov     r9d, 80420019h; char *
0x18004c3ac  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x18004c3b3  mov     edx, 1F3h; void *
0x18004c3b8  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c3be  movzx   r15d, byte ptr [rsp+980h+pvarg+8]
0x18004c3c4  lea     rdx, aEapcommonAutho; "./eapCommon:AuthorId"
0x18004c3cb  lea     rcx, [rbp+880h+var_8D0]
0x18004c3cf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004c3d4  nop
0x18004c3d5  lea     r9, [rsp+980h+pvarg]
0x18004c3da  mov     r8b, 1
0x18004c3dd  mov     rdx, rax
0x18004c3e0  mov     rcx, [rsp+980h+var_938]
0x18004c3e5  call    ?FindAndGetValue@XmlHelperModern@EapHost@@YA_NPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; EapHost::XmlHelperModern::FindAndGetValue(IXMLDOMNode *,std::wstring const &,bool,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &)
0x18004c3ea  nop
0x18004c3eb  lea     rcx, [rbp+880h+var_8D0]
0x18004c3ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c3f4  mov     esi, 3
0x18004c3f9  mov     edx, esi; int
0x18004c3fb  lea     rcx, [rsp+980h+pvarg]; pvarSrc
0x18004c400  call    ?VariantConvert@XmlHelperModern@EapHost@@YAJAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@G@Z; EapHost::XmlHelperModern::VariantConvert(wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &,ushort)
0x18004c405  test    eax, eax
0x18004c407  jns     short loc_18004C449
0x18004c409  test    cs:byte_180085041, 1
0x18004c410  jz      short loc_18004C41E
0x18004c412  lea     r8, aAuthorid; "AuthorId"
0x18004c419  call    McTemplateU0s_EventWriteTransfer
0x18004c41e  mov     rcx, [rbp+888h]; this
0x18004c425  lea     rax, aDatatypeMismat; "Datatype mismatch for AuthorId"
0x18004c42c  mov     [rsp+980h+lpBuffer], rax; int
0x18004c431  mov     r9d, 80420019h; char *
0x18004c437  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x18004c43e  mov     edx, 1FCh; void *
0x18004c443  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c449  mov     r12d, dword ptr [rsp+980h+pvarg+8]
0x18004c44e  mov     r14d, r13d
0x18004c451  lea     rdx, aEapcommonVendo; "./eapCommon:VendorId"
0x18004c458  lea     rcx, [rbp+880h+var_8D0]
0x18004c45c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004c461  nop
0x18004c462  lea     r9, [rsp+980h+pvarg]
0x18004c467  xor     r8d, r8d
0x18004c46a  mov     rdx, rax
0x18004c46d  mov     rcx, [rsp+980h+var_938]
0x18004c472  call    ?FindAndGetValue@XmlHelperModern@EapHost@@YA_NPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; EapHost::XmlHelperModern::FindAndGetValue(IXMLDOMNode *,std::wstring const &,bool,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &)
0x18004c477  mov     bl, al
0x18004c479  lea     rcx, [rbp+880h+var_8D0]
0x18004c47d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c482  test    bl, bl
0x18004c484  jz      short loc_18004C4DB
0x18004c486  mov     edx, esi; int
0x18004c488  lea     rcx, [rsp+980h+pvarg]; pvarSrc
0x18004c48d  call    ?VariantConvert@XmlHelperModern@EapHost@@YAJAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@G@Z; EapHost::XmlHelperModern::VariantConvert(wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &,ushort)
0x18004c492  test    eax, eax
0x18004c494  jns     short loc_18004C4D6
0x18004c496  test    cs:byte_180085041, 1
0x18004c49d  jz      short loc_18004C4AB
0x18004c49f  lea     r8, aVendorid; "VendorId"
0x18004c4a6  call    McTemplateU0s_EventWriteTransfer
0x18004c4ab  mov     rcx, [rbp+888h]; this
0x18004c4b2  lea     rax, aDatatypeMismat_0; "Datatype mismatch for VendorId"
0x18004c4b9  mov     [rsp+980h+lpBuffer], rax; int
0x18004c4be  mov     r9d, 80420019h; char *
0x18004c4c4  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x18004c4cb  mov     edx, 207h; void *
0x18004c4d0  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c4d6  mov     r14d, dword ptr [rsp+980h+pvarg+8]
0x18004c4db  mov     esi, r13d
0x18004c4de  lea     rdx, aEapcommonVendo_0; "./eapCommon:VendorType"
0x18004c4e5  lea     rcx, [rbp+880h+var_8D0]
0x18004c4e9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004c4ee  nop
0x18004c4ef  lea     r9, [rsp+980h+pvarg]
0x18004c4f4  xor     r8d, r8d
0x18004c4f7  mov     rdx, rax
0x18004c4fa  mov     rcx, [rsp+980h+var_938]
0x18004c4ff  call    ?FindAndGetValue@XmlHelperModern@EapHost@@YA_NPEAUIXMLDOMNode@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@@Z; EapHost::XmlHelperModern::FindAndGetValue(IXMLDOMNode *,std::wstring const &,bool,wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &)
0x18004c504  mov     bl, al
0x18004c506  lea     rcx, [rbp+880h+var_8D0]
0x18004c50a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c50f  test    bl, bl
0x18004c511  jz      short loc_18004C56A
0x18004c513  mov     edx, 3; int
0x18004c518  lea     rcx, [rsp+980h+pvarg]; pvarSrc
0x18004c51d  call    ?VariantConvert@XmlHelperModern@EapHost@@YAJAEAV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@G@Z; EapHost::XmlHelperModern::VariantConvert(wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &,ushort)
0x18004c522  test    eax, eax
0x18004c524  jns     short loc_18004C566
0x18004c526  test    cs:byte_180085041, 1
0x18004c52d  jz      short loc_18004C53B
0x18004c52f  lea     r8, aVendortype; "VendorType"
0x18004c536  call    McTemplateU0s_EventWriteTransfer
0x18004c53b  mov     rcx, [rbp+888h]; this
0x18004c542  lea     rax, aDatatypeMismat_1; "Datatype mismatch for VendorType"
0x18004c549  mov     [rsp+980h+lpBuffer], rax; int
0x18004c54e  mov     r9d, 80420019h; char *
0x18004c554  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x18004c55b  mov     edx, 213h; void *
0x18004c560  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c566  mov     esi, dword ptr [rsp+980h+pvarg+8]
0x18004c56a  mov     ecx, 4
0x18004c56f  cmp     r15b, cl
0x18004c572  jb      short loc_18004C586
0x18004c574  cmp     r15b, 0FEh
0x18004c578  jnz     loc_18004C62E
0x18004c57e  test    esi, esi
0x18004c580  jnz     loc_18004C63F
0x18004c586  test    cs:byte_180085041, 1
0x18004c58d  jz      short loc_18004C5F5
0x18004c58f  mov     [rsp+980h+var_908], esi
0x18004c593  mov     [rsp+980h+var_910], r14d
0x18004c598  mov     [rsp+980h+var_918], r12d
0x18004c59d  mov     [rsp+980h+var_940], r15b
0x18004c5a2  lea     rax, [rsp+980h+var_940]
0x18004c5a7  mov     [rbp+880h+var_880], rax
0x18004c5ab  mov     [rbp+880h+var_878], 1
0x18004c5b3  lea     rax, [rsp+980h+var_918]
0x18004c5b8  mov     [rbp+880h+var_870], rax
0x18004c5bc  mov     [rbp+880h+var_868], rcx
0x18004c5c0  lea     rax, [rsp+980h+var_910]
0x18004c5c5  mov     [rbp+880h+var_860], rax
0x18004c5c9  mov     [rbp+880h+var_858], rcx
0x18004c5cd  lea     rax, [rsp+980h+var_908]
0x18004c5d2  mov     [rbp+880h+var_850], rax
0x18004c5d6  mov     [rbp+880h+var_848], rcx
0x18004c5da  lea     rax, [rbp+880h+var_890]
0x18004c5de  mov     [rsp+980h+lpBuffer], rax
0x18004c5e3  mov     r9d, 5
0x18004c5e9  lea     rdx, XMLConfigError
0x18004c5f0  call    McGenEventWrite_EventWriteTransfer
0x18004c5f5  mov     rcx, [rbp+888h]; this
0x18004c5fc  mov     [rsp+980h+var_948], esi
0x18004c600  mov     dword ptr [rsp+980h+Arguments], r14d
0x18004c605  mov     dword ptr [rsp+980h+nSize], r15d; char *
0x18004c60a  lea     rax, aBadMethodTypeD; "Bad method: type(%d), VendorId(%d), Ven"...
0x18004c611  mov     [rsp+980h+lpBuffer], rax; int
0x18004c616  mov     r9d, 80420019h; char *
0x18004c61c  lea     r8, aOnecoreuapPriv; "onecoreuap\\private\\net\\inc\\eaphost"...
0x18004c623  mov     edx, 21Eh; void *
0x18004c628  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004c62e  test    r14d, r14d
0x18004c631  jnz     loc_18004C586
0x18004c637  test    esi, esi
0x18004c639  jnz     loc_18004C586
0x18004c63f  mov     [rdi+8], r15b
0x18004c643  mov     [rdi+0Ch], r14d
0x18004c647  mov     [rdi+10h], esi
0x18004c64a  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18004c651  mov     [rdi], rax
0x18004c654  mov     [rdi+18h], r12d
0x18004c658  lea     rcx, [rsp+980h+pvarg]; pvarg
0x18004c65d  call    cs:__imp_VariantClear
0x18004c663  nop
0x18004c664  lea     rcx, [rbp+880h+var_900]
0x18004c668  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004c66d  nop
0x18004c66e  lea     rcx, [rbp+880h+Src]
0x18004c672  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c677  nop
0x18004c678  cmp     [rsp+980h+var_938], r13
0x18004c67d  jz      short loc_18004C68A
0x18004c67f  lea     rcx, [rsp+980h+var_938]
0x18004c684  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x18004c689  nop
0x18004c68a  mov     rax, rdi
0x18004c68d  mov     rcx, [rbp+880h+var_40]
0x18004c694  xor     rcx, rsp; StackCookie
  ... truncated ...
```

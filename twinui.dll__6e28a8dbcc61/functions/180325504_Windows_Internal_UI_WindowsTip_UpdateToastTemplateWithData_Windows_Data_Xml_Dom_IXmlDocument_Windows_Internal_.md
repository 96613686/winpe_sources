# Windows::Internal::UI::WindowsTip::UpdateToastTemplateWithData(Windows::Data::Xml::Dom::IXmlDocument *,Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION const &,HSTRING__ *,HSTRING__ *,Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON const &,Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON const &,HSTRING__ *)

- ea: `0x180325504`
- end: `0x180325bdc`
- name: `?UpdateToastTemplateWithData@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@AEBUSOFTLANDING_NOTIFICATION@SoftLanding@234@PEAUHSTRING__@@2AEBUSOFTLANDING_BUTTON@SoftLanding@234@32@Z`
- size: `1752`
- prototype: `__int64 __usercall@<rax>(Windows::Internal::UI::WindowsTip *__hidden this@<rcx>, struct Windows::Data::Xml::Dom::IXmlDocument *@<rdx>, const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION *@<r8>, HSTRING@<r9>, HSTRING, const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *, const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *, HSTRING)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18031d638`

## callees

- `0x18000b7e8`
- `0x18000c350`
- `0x18003c5e4`
- `0x18003c898`
- `0x180052980`
- `0x1801321ac`
- `0x18013d330`
- `0x18021bfe4`
- `0x18021c1cc`
- `0x180312c00`
- `0x18031d14c`
- `0x18031d200`
- `0x18032251c`
- `0x180322818`
- `0x18032355c`
- `0x1803239b8`
- `0x180325504`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18032596a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803259b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180325a45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180325b7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180325ba5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18032596a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803259b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180325a45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180325b7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180325ba5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18032597f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18032597f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325572`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325587`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325599`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803255ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325941`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18032594f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325a55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325a65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325a73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325b25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325572`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325587`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325599`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803255ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325941`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18032594f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325a55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325a65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325a73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180325b25`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::UI::WindowsTip::UpdateToastTemplateWithData(
        Windows::Internal::UI::WindowsTip *this,
        HSTRING *a2,
        const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION *a3,
        HSTRING a4,
        struct Windows::Data::Xml::Dom::IXmlDocument *a5,
        const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *a6,
        const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *string)
{
  HSTRING v9; // r14
  unsigned __int16 *StringRawBuffer; // r13
  unsigned __int16 *v11; // rdi
  struct Windows::Data::Xml::Dom::IXmlDocument *v12; // rdx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 (__fastcall *v15)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, HSTRING *); // rbx
  int appended; // eax
  __int64 v22; // rdx
  unsigned int v23; // r14d
  int v24; // eax
  HSTRING v25; // rbx
  __int64 v26; // rax
  struct Windows::Data::Xml::Dom::IXmlNode *v27; // r8
  struct Windows::Data::Xml::Dom::IXmlNode **v28; // r9
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, _QWORD, HSTRING *); // rbx
  int v31; // eax
  int v32; // eax
  const unsigned __int16 *v33; // r9
  HSTRING v34; // rdi
  HSTRING v35; // r13
  HSTRING v36; // rbx
  __int64 v37; // rax
  struct Windows::Data::Xml::Dom::IXmlNode *v38; // r8
  struct Windows::Data::Xml::Dom::IXmlNode **v39; // r9
  PCWSTR v40; // rbx
  PCWSTR v41; // rax
  HRESULT v42; // eax
  unsigned int v43; // ebx
  __int64 (__fastcall *v45)(Windows::Internal::UI::WindowsTip *, GUID *, unsigned __int64 *); // rbx
  int v46; // eax
  const unsigned __int16 *v47; // rdi
  const unsigned __int16 *v48; // rbx
  Windows::Internal::UI::WindowsTip *v49; // rax
  int ActionString; // eax
  unsigned __int64 v51; // rdi
  __int64 (__fastcall *v52)(unsigned __int64, __int64, Windows::Internal::UI::WindowsTip **); // rbx
  int v53; // eax
  __int64 v54; // rdx
  const unsigned __int16 *v55; // rax
  const unsigned __int16 *v56; // r9
  HSTRING *v57; // [rsp+20h] [rbp-E8h]
  HSTRING v58; // [rsp+38h] [rbp-D0h]
  HSTRING newString; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int64 v60; // [rsp+48h] [rbp-C0h] BYREF
  Windows::Internal::UI::WindowsTip *v61; // [rsp+50h] [rbp-B8h] BYREF
  HSTRING v62; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v63; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v64; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 *v65; // [rsp+70h] [rbp-98h]
  const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *v66; // [rsp+78h] [rbp-90h]
  unsigned __int16 *v67; // [rsp+80h] [rbp-88h]
  HSTRING v68; // [rsp+88h] [rbp-80h]
  HSTRING v69; // [rsp+90h] [rbp-78h]
  struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *v70; // [rsp+98h] [rbp-70h]
  struct Windows::Data::Xml::Dom::IXmlDocument *v71; // [rsp+A0h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v73; // [rsp+C0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v68 = a4;
  v69 = (HSTRING)a3;
  v71 = a5;
  v70 = a6;
  v9 = (HSTRING)string;
  v66 = string;
  StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(*a2, 0);
  v62 = (HSTRING)StringRawBuffer;
  v61 = (Windows::Internal::UI::WindowsTip *)WindowsGetStringRawBuffer(a2[1], 0);
  v11 = (unsigned __int16 *)WindowsGetStringRawBuffer(a2[2], 0);
  v65 = v11;
  v67 = (unsigned __int16 *)WindowsGetStringRawBuffer(a2[3], 0);
  v60 = 0;
  v64 = 0;
  v13 = Windows::Internal::UI::WindowsTip::SetToastTemplateToToastGeneric(this, v12);
  v14 = v13;
  if ( v13 >= 0 )
  {
    v63 = 0;
    v15 = *(__int64 (__fastcall **)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *))(*(_QWORD *)this + 128LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
    v73 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"text", 5u, 4u);
    v16 = v15(this, v73, &v63);
    v14 = v16;
    if ( v16 < 0 )
    {
      v17 = 369;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v16,
        (int)v57);
      goto LABEL_53;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v63 + 48LL))(v63, &v64);
    if ( v18 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x172,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v18,
        (int)v57);
      goto LABEL_23;
    }
    if ( v64 )
    {
      newString = 0;
      v19 = v63;
      v20 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v63 + 56LL);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&newString);
      appended = v20(v19, 0, &newString);
      v14 = appended;
      if ( appended < 0 )
      {
        v22 = 374;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
          (const char *)(unsigned int)appended,
          (int)v57);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&newString);
LABEL_53:
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
        return v14;
      }
      v23 = 0;
      v24 = StringCchLengthW(StringRawBuffer, 0x7FFFFFFFu, &v60);
      if ( v24 >= 0 )
      {
        if ( v60 )
        {
          v25 = newString;
          v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v62);
          appended = Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(
                       *(Windows::Internal::UI::WindowsTip **)(v26 + 24),
                       v25,
                       v27,
                       v28);
          v14 = appended;
          if ( appended < 0 )
          {
            v22 = 378;
            goto LABEL_10;
          }
          v23 = 1;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x178,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
          (const char *)(unsigned int)v24,
          (int)v57);
      }
      if ( v64 > v23 )
      {
        v29 = v63;
        v30 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v63 + 56LL);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&newString);
        appended = v30(v29, v23, &newString);
        v14 = appended;
        if ( appended < 0 )
        {
          v22 = 384;
          goto LABEL_10;
        }
        v31 = StringCchLengthW((const unsigned __int16 *)v61, 0x7FFFFFFFu, &v60);
        if ( v31 >= 0 )
        {
          if ( v60 )
          {
            v36 = newString;
            v37 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v61);
            appended = Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(
                         *(Windows::Internal::UI::WindowsTip **)(v37 + 24),
                         v36,
                         v38,
                         v39);
            v14 = appended;
            if ( appended < 0 )
            {
              v22 = 388;
              goto LABEL_10;
            }
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x182,
            (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
            (const char *)(unsigned int)v31,
            (int)v57);
        }
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&newString);
      v11 = v65;
      v9 = (HSTRING)v66;
    }
LABEL_23:
    v32 = StringCchLengthW(v11, 0x104u, &v60);
    if ( v32 >= 0 )
    {
      if ( v60 )
      {
        v16 = Windows::Internal::UI::WindowsTip::SetToastImageSrc(
                this,
                (struct Windows::Data::Xml::Dom::IXmlDocument *)v11,
                v67,
                v33);
        v14 = v16;
        if ( v16 < 0 )
        {
          v17 = 395;
          goto LABEL_27;
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x189,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v32,
        (int)v57);
    }
    v34 = v68;
    v35 = v69;
    v16 = Windows::Internal::UI::WindowsTip::SetToastActions(
            this,
            v71,
            v70,
            (const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *)a2,
            (const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION *)v69,
            v68,
            v9,
            v58);
    v14 = v16;
    if ( v16 < 0 )
    {
      v17 = 405;
      goto LABEL_27;
    }
    if ( *((_DWORD *)a2 + 10) <= 1u )
    {
      newString = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SoftLandingV2>::GetImpl'::`2'::impl) )
      {
        v40 = WindowsGetStringRawBuffer(a2[4], 0);
        v41 = WindowsGetStringRawBuffer(v9, 0);
        try
        {
          Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::CreateActionString(&v62, v41, v40);
          WindowsDeleteString(newString);
          newString = 0;
          v42 = WindowsDuplicateString(v62, &newString);
        }
        catch ( ... )
        {
          LODWORD(v62) = *(_DWORD *)winrt::to_hresult(&v62);
          v14 = (unsigned int)v62;
          goto LABEL_50;
        }
        v43 = v42;
        if ( v42 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A2,
            (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
            (const char *)(unsigned int)v42,
            (int)v57);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v62);
          WindowsDeleteString(newString);
          newString = 0;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
          return v43;
        }
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v62);
      }
      else
      {
        WindowsDeleteString(newString);
        newString = 0;
        v47 = WindowsGetStringRawBuffer(v34, 0);
        v48 = WindowsGetStringRawBuffer(a2[4], 0);
        v49 = (Windows::Internal::UI::WindowsTip *)WindowsGetStringRawBuffer(v35, 0);
        ActionString = Windows::Internal::UI::WindowsTip::CreateActionString(
                         v49,
                         v48,
                         v47,
                         (const unsigned __int16 *)&newString,
                         v57);
        v14 = ActionString;
        if ( ActionString < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AF,
            (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
            (const char *)(unsigned int)ActionString,
            (int)v57);
LABEL_50:
          WindowsDeleteString(newString);
          newString = 0;
          goto LABEL_53;
        }
      }
      v60 = 0;
      v45 = **(__int64 (__fastcall ***)(Windows::Internal::UI::WindowsTip *, GUID *, unsigned __int64 *))this;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v60);
      v46 = v45(this, &GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b, &v60);
      v14 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B4,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
          (const char *)(unsigned int)v46,
          (int)v57);
LABEL_49:
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v60);
        goto LABEL_50;
      }
      v61 = 0;
      v51 = v60;
      v52 = *(__int64 (__fastcall **)(unsigned __int64, __int64, Windows::Internal::UI::WindowsTip **))(*(_QWORD *)v60 + 48LL);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v61);
      v73 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"toast", 6u, 5u);
      v53 = v52(v51, v73, &v61);
      v14 = v53;
      if ( v53 < 0 )
      {
        v54 = 438;
LABEL_48:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v54,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
          (const char *)(unsigned int)v53,
          (int)v57);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v61);
        goto LABEL_49;
      }
      v55 = WindowsGetStringRawBuffer(newString, 0);
      v53 = Windows::Internal::UI::WindowsTip::SetNodeAttribute(
              v61,
              (struct Windows::Data::Xml::Dom::IXmlNode *)L"launch",
              v55,
              v56);
      v14 = v53;
      if ( v53 < 0 )
      {
        v54 = 439;
        goto LABEL_48;
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v61);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v60);
      WindowsDeleteString(newString);
    }
    v14 = 0;
    goto LABEL_53;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16E,
    (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
    (const char *)(unsigned int)v13,
    (int)v57);
  return v14;
}

```

## disassembly

```asm
0x180325504  push    rbx
0x180325506  push    rsi
0x180325507  push    rdi
0x180325508  push    r12
0x18032550a  push    r13
0x18032550c  push    r14
0x18032550e  push    r15
0x180325510  sub     rsp, 0D0h
0x180325517  mov     rax, cs:__security_cookie
0x18032551e  xor     rax, rsp
0x180325521  mov     [rsp+108h+var_40], rax
0x180325529  mov     [rsp+108h+var_80], r9
0x180325531  mov     [rsp+108h+var_78], r8
0x180325539  mov     r12, rdx
0x18032553c  mov     r15, rcx
0x18032553f  mov     rax, [rsp+108h+arg_20]
0x180325547  mov     [rsp+108h+var_68], rax
0x18032554f  mov     rax, [rsp+108h+arg_28]
0x180325557  mov     [rsp+108h+var_70], rax
0x18032555f  mov     r14, [rsp+108h+string]
0x180325567  mov     [rsp+108h+var_90], r14
0x18032556c  xor     edx, edx; length
0x18032556e  mov     rcx, [r12]; string
0x180325572  call    cs:__imp_WindowsGetStringRawBuffer
0x180325578  mov     r13, rax
0x18032557b  mov     [rsp+108h+var_B0], rax
0x180325580  xor     edx, edx; length
0x180325582  mov     rcx, [r12+8]; string
0x180325587  call    cs:__imp_WindowsGetStringRawBuffer
0x18032558d  mov     [rsp+108h+var_B8], rax
0x180325592  xor     edx, edx; length
0x180325594  mov     rcx, [r12+10h]; string
0x180325599  call    cs:__imp_WindowsGetStringRawBuffer
0x18032559f  mov     rdi, rax
0x1803255a2  mov     [rsp+108h+var_98], rax
0x1803255a7  xor     edx, edx; length
0x1803255a9  mov     rcx, [r12+18h]; string
0x1803255ae  call    cs:__imp_WindowsGetStringRawBuffer
0x1803255b4  mov     [rsp+108h+var_88], rax
0x1803255bc  xor     esi, esi
0x1803255be  mov     [rsp+108h+var_C0], rsi
0x1803255c3  mov     [rsp+108h+var_A0], esi
0x1803255c7  mov     rcx, r15; this
0x1803255ca  call    ?SetToastTemplateToToastGeneric@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@@Z; Windows::Internal::UI::WindowsTip::SetToastTemplateToToastGeneric(Windows::Data::Xml::Dom::IXmlDocument *)
0x1803255cf  mov     ebx, eax
0x1803255d1  test    eax, eax
0x1803255d3  jns     short loc_1803255F6
0x1803255d5  mov     rcx, [rsp+108h]; this
0x1803255dd  mov     r9d, eax; char *
0x1803255e0  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x1803255e7  mov     edx, 16Eh; void *
0x1803255ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803255f1  jmp     loc_180325BB7
0x1803255f6  mov     [rsp+108h+var_A8], rsi
0x1803255fb  mov     rax, [r15]
0x1803255fe  mov     rbx, [rax+80h]
0x180325605  lea     rcx, [rsp+108h+var_A8]
0x18032560a  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18032560f  mov     [rsp+108h+var_48], rsi
0x180325617  mov     r9d, 4; unsigned int
0x18032561d  lea     r8d, [r9+1]; unsigned int
0x180325621  lea     rdx, aText_0; "text"
0x180325628  lea     rcx, [rsp+108h+hstringHeader]; hstringHeader
0x180325630  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180325635  nop
0x180325636  lea     r8, [rsp+108h+var_A8]
0x18032563b  mov     rdx, [rsp+108h+var_48]
0x180325643  mov     rcx, r15
0x180325646  mov     rax, rbx
0x180325649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18032564e  mov     ebx, eax
0x180325650  test    eax, eax
0x180325652  jns     short loc_18032565E
0x180325654  mov     edx, 171h
0x180325659  jmp     loc_180325885
0x18032565e  mov     rcx, [rsp+108h+var_A8]
0x180325663  mov     rax, [rcx]
0x180325666  lea     rdx, [rsp+108h+var_A0]
0x18032566b  mov     rax, [rax+30h]
0x18032566f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180325674  mov     rcx, [rsp+108h]; this
0x18032567c  test    eax, eax
0x18032567e  jns     short loc_180325699
0x180325680  mov     r9d, eax; char *
0x180325683  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18032568a  mov     edx, 172h; void *
0x18032568f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180325694  jmp     loc_180325806
0x180325699  cmp     [rsp+108h+var_A0], esi
0x18032569d  jbe     loc_180325806
0x1803256a3  mov     [rsp+108h+newString], rsi
0x1803256a8  mov     rdi, [rsp+108h+var_A8]
0x1803256ad  mov     rax, [rdi]
0x1803256b0  mov     rbx, [rax+38h]
0x1803256b4  lea     rcx, [rsp+108h+newString]
0x1803256b9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803256be  lea     r8, [rsp+108h+newString]
0x1803256c3  xor     edx, edx
0x1803256c5  mov     rcx, rdi
0x1803256c8  mov     rax, rbx
0x1803256cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803256d0  mov     ebx, eax
0x1803256d2  test    eax, eax
0x1803256d4  jns     short loc_180325702
0x1803256d6  mov     edx, 176h; void *
0x1803256db  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x1803256e2  mov     r9d, eax; char *
0x1803256e5  mov     rcx, [rsp+108h]; this
0x1803256ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803256f2  nop
0x1803256f3  lea     rcx, [rsp+108h+newString]
0x1803256f8  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803256fd  jmp     loc_180325BAD
0x180325702  mov     r14d, esi
0x180325705  lea     r8, [rsp+108h+var_C0]; unsigned __int64 *
0x18032570a  mov     edx, 7FFFFFFFh; unsigned __int64
0x18032570f  mov     rcx, r13; unsigned __int16 *
0x180325712  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180325717  mov     rcx, [rsp+108h]; this
0x18032571f  test    eax, eax
0x180325721  jns     short loc_180325739
0x180325723  mov     r9d, eax; char *
0x180325726  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18032572d  mov     edx, 178h; void *
0x180325732  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180325737  jmp     short loc_180325779
0x180325739  cmp     [rsp+108h+var_C0], rsi
0x18032573e  jbe     short loc_180325779
0x180325740  mov     rbx, [rsp+108h+newString]
0x180325745  lea     rdx, [rsp+108h+var_B0]
0x18032574a  lea     rcx, [rsp+108h+hstringHeader]
0x180325752  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180325757  mov     rdx, rbx; HSTRING
0x18032575a  mov     rcx, [rax+18h]; this
0x18032575e  call    ?CreateAndAppendTextNode@WindowsTip@UI@Internal@Windows@@YAJPEAUHSTRING__@@PEAUIXmlNode@Dom@Xml@Data@4@PEAPEAU67894@@Z; Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(HSTRING__ *,Windows::Data::Xml::Dom::IXmlNode *,Windows::Data::Xml::Dom::IXmlNode * *)
0x180325763  mov     ebx, eax
0x180325765  test    eax, eax
0x180325767  jns     short loc_180325773
0x180325769  mov     edx, 17Ah
0x18032576e  jmp     loc_1803256DB
0x180325773  mov     r14d, 1
0x180325779  cmp     [rsp+108h+var_A0], r14d
0x18032577e  jbe     short loc_1803257F2
0x180325780  mov     rdi, [rsp+108h+var_A8]
0x180325785  mov     rax, [rdi]
0x180325788  mov     rbx, [rax+38h]
0x18032578c  lea     rcx, [rsp+108h+newString]
0x180325791  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180325796  lea     r8, [rsp+108h+newString]
0x18032579b  mov     edx, r14d
0x18032579e  mov     rcx, rdi
0x1803257a1  mov     rax, rbx
0x1803257a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803257a9  mov     ebx, eax
0x1803257ab  test    eax, eax
0x1803257ad  jns     short loc_1803257B9
0x1803257af  mov     edx, 180h
0x1803257b4  jmp     loc_1803256DB
0x1803257b9  lea     r8, [rsp+108h+var_C0]; unsigned __int64 *
0x1803257be  mov     edx, 7FFFFFFFh; unsigned __int64
0x1803257c3  mov     rcx, [rsp+108h+var_B8]; unsigned __int16 *
0x1803257c8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1803257cd  mov     rcx, [rsp+108h]; this
0x1803257d5  test    eax, eax
0x1803257d7  jns     loc_1803258A1
0x1803257dd  mov     r9d, eax; char *
0x1803257e0  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x1803257e7  mov     edx, 182h; void *
0x1803257ec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1803257f1  nop
0x1803257f2  lea     rcx, [rsp+108h+newString]
0x1803257f7  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803257fc  mov     rdi, [rsp+108h+var_98]
0x180325801  mov     r14, [rsp+108h+var_90]
0x180325806  lea     r8, [rsp+108h+var_C0]; unsigned __int64 *
0x18032580b  mov     edx, 104h; unsigned __int64
0x180325810  mov     rcx, rdi; unsigned __int16 *
0x180325813  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180325818  mov     rcx, [rsp+108h]; this
0x180325820  test    eax, eax
0x180325822  jns     loc_1803258E3
0x180325828  mov     r9d, eax; char *
0x18032582b  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180325832  mov     edx, 189h; void *
0x180325837  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18032583c  mov     [rsp+108h+var_D8], r14; HSTRING
0x180325841  mov     rdi, [rsp+108h+var_80]
0x180325849  mov     [rsp+108h+var_E0], rdi; HSTRING
0x18032584e  mov     r13, [rsp+108h+var_78]
0x180325856  mov     [rsp+108h+var_E8], r13; int
0x18032585b  mov     r9, r12; struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *
0x18032585e  mov     r8, [rsp+108h+var_70]; struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *
0x180325866  mov     rdx, [rsp+108h+var_68]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x18032586e  mov     rcx, r15; this
0x180325871  call    ?SetToastActions@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@AEBUSOFTLANDING_BUTTON@SoftLanding@234@1AEBUSOFTLANDING_NOTIFICATION@SoftLanding@234@PEAUHSTRING__@@33@Z; Windows::Internal::UI::WindowsTip::SetToastActions(Windows::Data::Xml::Dom::IXmlDocument *,Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON const &,Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON const &,Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION const &,HSTRING__ *,HSTRING__ *,HSTRING__ *)
0x180325876  mov     ebx, eax
0x180325878  test    eax, eax
0x18032587a  jns     loc_180325915
0x180325880  mov     edx, 195h; void *
0x180325885  mov     r9d, eax; char *
0x180325888  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18032588f  mov     rcx, [rsp+108h]; this
0x180325897  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18032589c  jmp     loc_180325BAD
0x1803258a1  cmp     [rsp+108h+var_C0], rsi
0x1803258a6  jbe     loc_1803257F2
0x1803258ac  mov     rbx, [rsp+108h+newString]
0x1803258b1  lea     rdx, [rsp+108h+var_B8]
0x1803258b6  lea     rcx, [rsp+108h+hstringHeader]
0x1803258be  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1803258c3  mov     rdx, rbx; HSTRING
0x1803258c6  mov     rcx, [rax+18h]; this
0x1803258ca  call    ?CreateAndAppendTextNode@WindowsTip@UI@Internal@Windows@@YAJPEAUHSTRING__@@PEAUIXmlNode@Dom@Xml@Data@4@PEAPEAU67894@@Z; Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(HSTRING__ *,Windows::Data::Xml::Dom::IXmlNode *,Windows::Data::Xml::Dom::IXmlNode * *)
0x1803258cf  mov     ebx, eax
0x1803258d1  test    eax, eax
0x1803258d3  jns     loc_1803257F2
0x1803258d9  mov     edx, 184h
0x1803258de  jmp     loc_1803256DB
0x1803258e3  cmp     [rsp+108h+var_C0], rsi
0x1803258e8  jbe     loc_18032583C
0x1803258ee  mov     r8, [rsp+108h+var_88]; unsigned __int16 *
0x1803258f6  mov     rdx, rdi; struct Windows::Data::Xml::Dom::IXmlDocument *
0x1803258f9  mov     rcx, r15; this
0x1803258fc  call    ?SetToastImageSrc@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@PEBG1@Z; Windows::Internal::UI::WindowsTip::SetToastImageSrc(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,ushort const *)
0x180325901  mov     ebx, eax
0x180325903  test    eax, eax
0x180325905  jns     loc_18032583C
0x18032590b  mov     edx, 18Bh
0x180325910  jmp     loc_180325885
0x180325915  cmp     dword ptr [r12+28h], 1
0x18032591b  ja      loc_180325BAB
0x180325921  mov     [rsp+108h+newString], rsi
0x180325926  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SoftLandingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SoftLandingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2> `wil::Feature<__WilFeatureTraits_Feature_SoftLandingV2>::GetImpl(void)'::`2'::impl
0x18032592d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SoftLandingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2>::__private_IsEnabled(void)
0x180325932  test    al, al
0x180325934  jz      loc_180325A40
0x18032593a  xor     edx, edx; length
0x18032593c  mov     rcx, [r12+20h]; string
0x180325941  call    cs:__imp_WindowsGetStringRawBuffer
0x180325947  mov     rbx, rax
0x18032594a  xor     edx, edx; length
0x18032594c  mov     rcx, r14; string
0x18032594f  call    cs:__imp_WindowsGetStringRawBuffer
0x180325955  mov     r8, rbx
0x180325958  mov     rdx, rax
0x18032595b  lea     rcx, [rsp+108h+var_B0]
0x180325960  call    ?CreateActionString@SoftLandingV2Helper@WindowsTip@UI@Internal@Windows@@SA?AUhstring@winrt@@PEBG0@Z; Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::CreateActionString(ushort const *,ushort const *)
0x180325965  mov     rcx, [rsp+108h+newString]; string
0x18032596a  call    cs:__imp_WindowsDeleteString
0x180325970  mov     [rsp+108h+newString], rsi
0x180325975  lea     rdx, [rsp+108h+newString]; newString
0x18032597a  mov     rcx, [rsp+108h+var_B0]; string
0x18032597f  call    cs:__imp_WindowsDuplicateString
0x180325985  mov     ebx, eax
0x180325987  test    eax, eax
0x180325989  jns     short loc_1803259D3
0x18032598b  mov     rcx, [rsp+108h]; this
0x180325993  mov     r9d, eax; char *
0x180325996  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18032599d  mov     edx, 1A2h; void *
0x1803259a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803259a7  lea     rcx, [rsp+108h+var_B0]
0x1803259ac  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1803259b1  nop
0x1803259b2  mov     rcx, [rsp+108h+newString]; string
0x1803259b7  call    cs:__imp_WindowsDeleteString
0x1803259bd  mov     [rsp+108h+newString], rsi
0x1803259c2  lea     rcx, [rsp+108h+var_A8]
0x1803259c7  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803259cc  mov     eax, ebx
0x1803259ce  jmp     loc_180325BB9
0x1803259d3  lea     rcx, [rsp+108h+var_B0]
0x1803259d8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1803259dd  nop
0x1803259de  mov     [rsp+108h+var_C0], rsi
0x1803259e3  mov     rax, [r15]
0x1803259e6  mov     rbx, [rax]
0x1803259e9  lea     rcx, [rsp+108h+var_C0]
0x1803259ee  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803259f3  lea     r8, [rsp+108h+var_C0]
0x1803259f8  lea     rdx, _GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b
0x1803259ff  mov     rcx, r15
0x180325a02  mov     rax, rbx
0x180325a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180325a0a  mov     ebx, eax
0x180325a0c  test    eax, eax
0x180325a0e  jns     loc_180325AB7
0x180325a14  mov     rcx, [rsp+108h]; this
0x180325a1c  mov     r9d, eax; char *
0x180325a1f  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180325a26  mov     edx, 1B4h; void *
0x180325a2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180325a30  jmp     loc_180325B6D
0x180325a35  mov     ebx, dword ptr [rsp+108h+var_B0]
0x180325a39  xor     esi, esi
0x180325a3b  jmp     loc_180325B78
0x180325a40  mov     rcx, [rsp+108h+newString]; string
0x180325a45  call    cs:__imp_WindowsDeleteString
0x180325a4b  mov     [rsp+108h+newString], rsi
0x180325a50  xor     edx, edx; length
  ... truncated ...
```
